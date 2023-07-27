# PowerShell

| Command                                                            | Description                      |
| ------------------------------------------------------------------ | -------------------------------- |
| `Connect-AzAccount`                                                | login to azure with your account |
| `Get-AzSubscription`                                               | -                                |
| `Set-AzContext -Subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | use subscriptionID               |
| `Get-AzContext`                                                    | -                                |
| `Get-AzResourceGroup \| Format-Table`                              | -                                |
| `Get-AzLocation \| Format-Table -Property Location, DisplayName`   | -                                |

## Index

- [Create rg][100]
- [Create vnet][101]
- [Create snet][102]
- [Create pip][103]
- [Azure Firewall Premium Hands on Lab][6]
- [Azure Watcher Connection Monitor][104]

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

## Create an Azure Network Watcher Connection Monitor

```PowerShell
# Connect to your Azure account with the subscription
Connect-AzAccount
Select-AzSubscription -SubscriptionId <your-subscription>
# Select region

$nw = "NetworkWatcher_eastus"
# Declare endpoints like Azure VM below. You can also give VNET,Subnet,Log Analytics workspace
$sourcevmid1 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name MyAzureVm -ResourceID /subscriptions/<your-subscription>/resourceGroups/<your resourceGroup>/providers/Microsoft.Compute/virtualMachines/<vm-name>
# Declare endpoints like URL, IPs
$bingEndpoint = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name Bing -Address www.bing.com # Destination URL

# Create test configuration.Choose Protocol and parametersSample configs below.
$icmpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -IcmpProtocol
$tcpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -TcpProtocol -Port 80
$httpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -HttpProtocol -Port 443 -Method GET -RequestHeader @{Allow = "GET"} -ValidStatusCodeRange 2xx, 300-308 -PreferHTTPS

# Create test configuration with protocol configuration
$httpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name http-tc -TestFrequencySec 60 -ProtocolConfiguration $httpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 30
$icmpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name icmp-tc -TestFrequencySec 30 -ProtocolConfiguration $icmpProtocolConfiguration -SuccessThresholdChecksFailedPercent 5 -SuccessThresholdRoundTripTimeMs 500
$tcpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name tcp-tc -TestFrequencySec 60 -ProtocolConfiguration $tcpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 30

# Create Test Group
$testGroup1 = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name testGroup1 -TestConfiguration $httpTestConfiguration, $tcpTestConfiguration, $icmpTestConfiguration -Source $sourcevmid1 -Destination $bingEndpoint,
$testname = "cmtest9"

# Create Connection Monitor
New-AzNetworkWatcherConnectionMonitor -NetworkWatcherName $nw -ResourceGroupName NetworkWatcherRG -Name $testname -TestGroup $testGroup1





$ConnectionMonitorVars = @{
    Name = "your-connection-monitor-name"
    Location = 'EastUS2'
    SourceResourceId = 'your-source-resource-id'
    DestinationResourceId = 'your-destination-resource-id'
    Tag = @{
        "your-key" = "your-value"
    }
    ResourceGroupName = 'rgName'
}

# Create a connection monitor
$ConnectionMonitor = New-AzNetworkWatcherConnectionMonitor @ConnectionMonitorVars
```

## Additional Resources

- [ALK | Lab | Azure Firewall Premium][6]
- [MS | Docs | Get-AzLocations][1]
- [MS | Docs | New-AzResourceGroup][2]
- [MS | Docs | New-AzVirtualNetwork][3]
- [MS | Docs | Add-AzVirtualNetworkSubnetConfig][4]
- [MS | Docs | New-AzPublicIpAddress][5]
- Connection Monitor
- [MS | Learn | Create an Azure Network Watcher connection monitor using the Azure portal][7]

<!-- Reference Links -->

[1]: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-azlocation?view=azps-5.7.0
[2]: https://docs.microsoft.com/en-us/powershell/module/az.resources/new-azresourcegroup?view=azps-5.7.0
[3]: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azvirtualnetwork?view=azps-5.7.0
[4]: https://docs.microsoft.com/en-us/powershell/module/az.network/add-azvirtualnetworksubnetconfig?view=azps-5.7.0
[5]: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azpublicipaddress?view=azps-5.7.0
[6]: https://github.com/ArtiomLK/azure-firewall-premium-lab
[7]: https://learn.microsoft.com/en-us/azure/network-watcher/connection-monitor-create-using-portal
[100]: #create-rg
[101]: #create-vnet
[102]: #create-snet
[103]: #create-pip
[104]: #create-an-azure-network-watcher-connection-monitor
