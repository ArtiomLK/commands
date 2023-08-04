# Connection Monitor

```PowerShell
# Sources must be in the same region as the network watcher
# Destinations can be in any region
# We must install Network Watcher Extensions on the source VMs

# Connect to your Azure account with the subscription
Connect-AzAccount
Select-AzSubscription -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

# Replace the following required variables
$nw = "NetworkWatcher_eastus2"
$connectionMonitorName = "cm-app1-prod-eastus2"

# get the VMs
$vm1 = Get-AzVM -ResourceGroupName "rg-app1-prod-eastus2" -Name "vm-app1-prod-eastus2"

# Install Azure Network Watcher Extension on the Source VMs
Set-AzVMExtension -ResourceGroupName $vm1.ResourceGroupName -VMName $vm1.Name -Name "NetworkWatcherAgentWindows" -Publisher "Microsoft.Azure.NetworkWatcher" -ExtensionType "NetworkWatcherAgentWindows" -TypeHandlerVersion "1.4" -EnableAutomaticUpgrade $true

# ------------------------------------------------------------------------------------------------
# Create an Azure Network Watcher Connection Monitor to test connectivity to on-premises
# ------------------------------------------------------------------------------------------------
$tg1 = "tg-$($vm1.Name)-to-on-prem-db"

# Sources
$sourceVm1 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm1.Name)-$($vm1.Location)" -ResourceID $vm1.id

# Destinations
$endpoint1 = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "endpoint1" -Address 10.10.10.10
$endpoint2 = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "endpoint2" -Address 10.10.10.11
$endpoint3 = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "endpoint3" -Address 10.10.10.12

# Create test configuration.Choose Protocol and parametersSample configs below.
$icmpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -IcmpProtocol

# Create test configuration with protocol configuration
$icmpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name icmp-tc -TestFrequencySec 60 -ProtocolConfiguration $icmpProtocolConfiguration -SuccessThresholdChecksFailedPercent 5 -SuccessThresholdRoundTripTimeMs 100

# Create Test Group
$tg_ref1 = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name $tg1 -TestConfiguration $icmpTestConfiguration -Source $sourceVm1 -Destination $endpoint1,$endpoint2,$endpoint3

# ------------------------------------------------------------------------------------------------
# Create Connection Monitor and confirm to all
New-AzNetworkWatcherConnectionMonitor -NetworkWatcherName $nw -ResourceGroupName NetworkWatcherRG -Name $connectionMonitorName -TestGroup $tg_ref1 -Force
```
