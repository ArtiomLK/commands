# Connection Monitor

```PowerShell
# Sources must be in the same region as the network watcher
# Destinations can be in any region
# We must install Network Watcher Extensions on the source VMs

# Connect to your Azure account with the subscription
Connect-AzAccount
Select-AzSubscription -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

# Replace the following required variables
$nw = "NetworkWatcher_centralus"
$connectionMonitorName = "cm-app2-prod-centralus"

# get the VMs
$vm1 = Get-AzVM -ResourceGroupName "rg-app2-prod-centralus" -Name "vm-app2-prod-centralus-001"
$vm2 = Get-AzVM -ResourceGroupName "rg-app2-prod-centralus" -Name "vm-app2-prod-centralus-002"

# # Install Azure Network Watcher Extension on the Source VMs
Set-AzVMExtension -ResourceGroupName $vm1.ResourceGroupName -VMName $vm1.Name -Name "NetworkWatcherAgentWindows" -Publisher "Microsoft.Azure.NetworkWatcher" -ExtensionType "NetworkWatcherAgentWindows" -TypeHandlerVersion "1.4" -EnableAutomaticUpgrade $true
Set-AzVMExtension -ResourceGroupName $vm2.ResourceGroupName -VMName $vm2.Name -Name "NetworkWatcherAgentWindows" -Publisher "Microsoft.Azure.NetworkWatcher" -ExtensionType "NetworkWatcherAgentWindows" -TypeHandlerVersion "1.4" -EnableAutomaticUpgrade $true

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
$endpoint4 = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "endpoint4" -Address 10.10.10.13
$endpoint5 = New-AzNetworkWatcherConnectionMonitorEndpointObject -ExternalAddress -Name "endpoint5" -Address 10.10.10.14

# Create test configuration.Choose Protocol and parametersSample configs below.
$tcpProtocolConfiguration = New-AzNetworkWatcherConnectionMonitorProtocolConfigurationObject -TcpProtocol -Port 1533

# Create test configuration with protocol configuration
$tcpTestConfiguration = New-AzNetworkWatcherConnectionMonitorTestConfigurationObject -Name tcp-tc -TestFrequencySec 60 -ProtocolConfiguration $tcpProtocolConfiguration -SuccessThresholdChecksFailedPercent 20 -SuccessThresholdRoundTripTimeMs 500

# Create Test Group
$tg_ref1 = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name $tg1 -TestConfiguration $tcpTestConfiguration -Source $sourceVm1 -Destination $endpoint1,$endpoint2,$endpoint3,$endpoint4,$endpoint5

# ------------------------------------------------------------------------------------------------
# Create an Azure Network Watcher Connection Monitor to test connectivity to on-premises VM 2
# ------------------------------------------------------------------------------------------------
# Sources
$sourceVm2 = New-AzNetworkWatcherConnectionMonitorEndpointObject -AzureVM -Name "$($vm2.Name)-$($vm2.Location)" -ResourceID $vm2.id

$tg2 = "tg-$($vm2.Name)-to-on-prem-db"

# Create Test Group
$tg_ref2 = New-AzNetworkWatcherConnectionMonitorTestGroupObject -Name $tg2 -TestConfiguration $tcpTestConfiguration -Source $sourceVm2 -Destination $endpoint1,$endpoint2,$endpoint3,$endpoint4,$endpoint5

# Create Connection Monitor and confirm to all
New-AzNetworkWatcherConnectionMonitor -NetworkWatcherName $nw -ResourceGroupName NetworkWatcherRG -Name $connectionMonitorName -TestGroup $tg_ref1,$tg_ref2 -Force
```
