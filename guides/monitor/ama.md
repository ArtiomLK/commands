# Azure Monitoring Agent (AMA)

## Enable Monitoring Agent on Azure VMs

- [Azure Monitor Agent overview][4]
  - Install AMA Agent [Microsoft.Azure.Monitor.AzureMonitorWindowsAgent][12]
  - Uninstall Log Analytics Agent [Microsoft.EnterpriseCloud.Monitoring.MicrosoftMonitoringAgent][11]
  - Check Agent Duplicates
    - `Heartbeat    | summarize max(TimeGenerated) by Computer, Category    | sort by Computer`
  - [Supported operating systems][8]
  - [Install the AMA agent and configure data collection AMA][6]
  - [Enable automatic upgrade VM-> Extensions + Applications -> AzureMonitorWindowsAgent ->  click on Enable automatic upgrade][7]
- [Performance diagnostics for Azure virtual machines][8]
  - [Supported operating systems][9]
  - [Install and run performance diagnostics on your VM][10]

## Additional Resources

- Monitoring
- [MS | Learn | Azure Monitor Agent overview][4]
- [MS | Learn | Azure Monitor Agent overview | Install the agent and configure data collection][6]
- [MS | Learn | Azure Monitor Agent overview | Supported operating systems][8]
- [MS | Learn | Manage Azure Monitor Agent | Update][7]
- [MS | Learn | Migrate to Azure Monitor Agent from Log Analytics agent][5]

[4]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview
[5]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration
[6]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview#install-the-agent-and-configure-data-collection
[7]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal#update
[8]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics
[9]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics#supported-operating-systems
[10]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics#install-and-run-performance-diagnostics-on-your-vm
[11]: https://learn.microsoft.com/en-us/azure/virtual-machines/extensions/oms-windows#extension-schema
[12]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal#virtual-machine-extension-details
