# PowerShell

| Command                                                            | Description                      |
| ------------------------------------------------------------------ | -------------------------------- |
| `Connect-AzAccount`                                                | login to azure with your account |
| `Connect-AzAccount -Tenant xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`   |                                  |
| `Get-AzSubscription`                                               | -                                |
| `Set-AzContext -Subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | use subscriptionID               |
| `Get-AzContext`                                                    | -                                |
| `Get-AzResourceGroup \| Format-Table`                              | -                                |
| `Get-AzLocation \| Format-Table -Property Location, DisplayName`   | -                                |

- [PowerShell](#powershell)
  - [Create rg](#create-rg)
  - [Create vnet](#create-vnet)
  - [Create snet](#create-snet)
  - [Create pip](#create-pip)
  - [Start and Stop agw](#start-and-stop-agw)
  - [Set Subscription Key in APIM](#set-subscription-key-in-apim)
  - [Create an Azure Network Watcher Connection Monitor](#create-an-azure-network-watcher-connection-monitor)
  - [Additional Resources](#additional-resources)

## Create rg

Run the following commands in PowerShell to create an Azure Resource Group

```PowerShell
# Replace the following required Azure Resource Group variables
$rg = @{
    Name = 'your-rg-name'
    Location = 'EastUS2'
}

# Create an Azure ResourceGroup
New-AzResourceGroup @rg
```

## Create vnet

Run the following commands in PowerShell to create an Azure Virtual Network

```PowerShell
# Replace the following required Azure Virtual Network variables
$vNet = @{
    Name = 'vNetName'
    ResourceGroupName = 'rgName'
    Location = 'EastUS2'
    AddressPrefix = '10.0.0.0/16'
}

# Create the VNet
$virtualNetwork = New-AzVirtualNetwork @vnet
```

## Create snet

Run the following commands in PowerShell to add a subnet to an existing Azure Virtual Network

```PowerShell
# Gather our existing Azure vNet
$vNet = Get-AzVirtualNetwork -Name 'vNetName' -ResourceGroup 'rgName'

# Replace the following required Azure Virtual Network variables
$subNet = @{
    Name = 'snet-name'
    AddressPrefix = 'your-address-prefix' #e.g. '10.0.0.0/24'
}

# Add the subnet to our Azure Virtual Network
$virtualNetwork | Add-AzVirtualNetworkSubnetConfig -Name $subNet.Name -AddressPrefix $subNet.AddressPrefix
$virtualNetwork | Set-AzVirtualNetwork
```

## Create pip

Run the following commands in PowerShell to create an Azure Public IP

```PowerShell
# Replace the following required variables
$PublicIpVars = @{
    Name = "your-public-ip-name"
    Location = 'EastUS2'
    AllocationMethod = "Static"
    Sku = "Standard"
    Zone = "1", "2", "3"
    ResourceGroupName = 'rgName'
}

# Deploy a zone-redundant public IP
$PublicIp = New-AzPublicIpAddress @PublicIpVars
```

## Start and Stop agw

```PowerShell
$AppGW = Get-AzApplicationGateway -Name "agw_name" -ResourceGroupName "rg_name"

Stop-AzApplicationGateway -ApplicationGateway $AppGW

Start-AzApplicationGateway -ApplicationGateway $AppGW
```

## Set Subscription Key in APIM

```PowerShell
$source = New-AzApiManagementContext -ResourceGroupName "<rg_name_apim1>" -ServiceName "<rg_name_apim1>"; echo $source
$target = New-AzApiManagementContext -ResourceGroupName "<rg_name_apim2>" -ServiceName "<rg_name_apim2>"; echo $target

$keySet = Get-AzApiManagementSubscriptionKey -Context $source -SubscriptionId "master"; echo $keySet
Set-AzApiManagementSubscription -Context $target -SubscriptionId "master" -PrimaryKey $keySet.PrimaryKey -SecondaryKey $keySet.SecondaryKey
```

## Create an Azure Network Watcher Connection Monitor

```PowerShell
# Sources must be in the same region as the network watcher
# Destinations can be in any region
# We must install Network Watcher Extensions on the source VMs
# Additional examples at /examples/cm

# Connect to your Azure account with the subscription
Connect-AzAccount
Select-AzSubscription -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

# Replace the following required variables
$nw = "NetworkWatcher_eastus"
$connectionMonitorName = "cm-topology-dev-eastus"

# get the VMs
$vm1 = Get-AzVM -ResourceGroupName "rg-az-bicep-topology-dev-eastus" -Name "vm-spoke-1-a827"
$vm2 = Get-AzVM -ResourceGroupName "rg-az-bicep-topology-dev-eastus" -Name "vm-spoke-n-8d4a"

# Install Azure Network Watcher Extension on the Source VMs
Set-AzVMExtension -ResourceGroupName $vm1.ResourceGroupName -VMName $vm1.Name -Name "NetworkWatcherAgentWindows" -Publisher "Microsoft.Azure.NetworkWatcher" -ExtensionType "NetworkWatcherAgentWindows" -TypeHandlerVersion "1.4" -EnableAutomaticUpgrade $true
Set-AzVMExtension -ResourceGroupName $vm2.ResourceGroupName -VMName $vm2.Name -Name "NetworkWatcherAgentWindows" -Publisher "Microsoft.Azure.NetworkWatcher" -ExtensionType "NetworkWatcherAgentWindows" -TypeHandlerVersion "1.4" -EnableAutomaticUpgrade $true

# *** If required Enable ICMP on the VM ***
# ------------------------------------------------------------------------------------------------
$vmOnPrem = Get-AzVM -ResourceGroupName "rg-az-bicep-topology-on-prem-dev-eastus" -Name "vm-on-prem-1-02"
# run Powershell command on vm
Invoke-AzVMRunCommand -ResourceGroupName $vmOnPrem.ResourceGroupName -VMName $vmOnPrem.Name -CommandId 'RunPowerShellScript' -ScriptPath 'ps\enable_icmp.ps1'
# ------------------------------------------------------------------------------------------------

# ------------------------------------------------------------------------------------------------
# Create an Azure Network Watcher Connection Monitor to test connectivity to on-premises
# ------------------------------------------------------------------------------------------------
$testGroupOnPremName = "test-group-az-eastus-to-on-prem"

# Sources
$sourceVm1 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm1.Name)-$($vm1.Location)" -ResourceID $vm1.id
$sourceVm2 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm2.Name)-$($vm2.Location)" -ResourceID $vm2.id

# Destinations
$endpointBing = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "Bing" -Address www.bing.com
$endpointOnPremVm = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "vm-on-prem-1-02" -Address 192.168.1.244

# Create test configuration.Choose Protocol and parametersSample configs below.
$icmpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -IcmpProtocol
$tcpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -TcpProtocol -Port 3389

# Create test configuration with protocol configuration
$icmpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name icmp-tc -TestFrequencySec 60 -ProtocolConfiguration $icmpProtocolConfiguration -SuccessThresholdChecksFailedPercent 5 -SuccessThresholdRoundTripTimeMs 100
$tcpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name tcp-tc -TestFrequencySec 60 -ProtocolConfiguration $tcpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 100

# Create Test Group
$testGroupOnPremRef = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name $testGroupOnPremName -TestConfiguration $tcpTestConfiguration, $icmpTestConfiguration -Source $sourceVm1, $sourceVm2 -Destination $endpointOnPremVm

# ------------------------------------------------------------------------------------------------
# Create an Azure Network Watcher Connection Monitor to test connectivity to the Internet
# ------------------------------------------------------------------------------------------------
$testGroupInternetName = "test-group-az-eastus-to-internet"

# Sources
$sourceVm1 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm1.Name)-$($vm1.Location)" -ResourceID $vm1.id
$sourceVm2 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm2.Name)-$($vm2.Location)" -ResourceID $vm2.id

# Destinations
$endpointBing = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "Bing" -Address www.bing.com

# Create test configuration.Choose Protocol and parametersSample configs below.
$httpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -HttpProtocol -Port 80 -Method GET -RequestHeader @{Allow = "GET"} -ValidStatusCodeRange 2xx, 300-308
$httpsProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -HttpProtocol -Port 443 -Method GET -RequestHeader @{Allow = "GET"} -ValidStatusCodeRange 2xx, 300-308 -PreferHTTPS
$tcpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -TcpProtocol -Port 80

# Create test configuration with protocol configuration
$httpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name http-tc -TestFrequencySec 60 -ProtocolConfiguration $httpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 200
$httpsTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name https-tc -TestFrequencySec 60 -ProtocolConfiguration $httpsProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 200

# Create Test Group
$testGroupInternetRef = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name $testGroupInternetName -TestConfiguration $httpTestConfiguration, $httpsTestConfiguration -Source $sourceVm1, $sourceVm2 -Destination $endpointBing

# Create Connection Monitor and confirm to all
New-AzNetworkWatcherConnectionMonitor -NetworkWatcherName $nw -ResourceGroupName NetworkWatcherRG -Name $connectionMonitorName -TestGroup $testGroupOnPremRef, $testGroupInternetRef -Force
```

## Additional Resources

- [ALK | Lab | Azure Firewall Premium][6]
- [MS | Docs | Get-AzLocations][1]
- [MS | Docs | New-AzResourceGroup][2]
- [MS | Docs | New-AzVirtualNetwork][3]
- [MS | Docs | Add-AzVirtualNetworkSubnetConfig][4]
- [MS | Docs | New-AzPublicIpAddress][5]
- Connection Monitor
- [MS | Learn | Create an Azure Network Watcher connection monitor using PowerShell][7]

[1]: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-azlocation?view=azps-5.7.0
[2]: https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroup?view=azps-5.7.0
[3]: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azvirtualnetwork?view=azps-5.7.0
[4]: https://docs.microsoft.com/en-us/powershell/module/az.network/add-azvirtualnetworksubnetconfig?view=azps-5.7.0
[5]: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azpublicipaddress?view=azps-5.7.0
[6]: https://github.com/ArtiomLK/azure-firewall-premium-lab
[7]: https://learn.microsoft.com/en-us/azure/network-watcher/connection-monitor-create-using-powershell
