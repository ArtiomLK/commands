# Azure Monitoring Agent (AMA)

## Enable Monitoring Agent on Azure VMs

- Validate all requirements
  - [Azure Monitor Agent Supported operating systems][3]
  - [Azure Monitor Agent Prerequisites][1]
  - [Performance diagnostics for Azure virtual machines | Supported operating systems][2]
- Install [Azure Monitor Agent][4]
  - [Install the AMA (Microsoft.Azure.Monitor.AzureMonitorWindowsAgent) agent and configure data collection AMA][6]
  - [Enable automatic upgrade VM-> Extensions + Applications -> AzureMonitorWindowsAgent ->  click on Enable automatic upgrade][7]
- Avoid Agent Duplicates costs
  - [Heartbeat | summarize max(TimeGenerated) by Computer, Category | sort by Computer][12]
  - Uninstalling Log Analytics Agent [Microsoft.EnterpriseCloud.Monitoring.MicrosoftMonitoringAgent][11]
    - Review Az policies that automate installing log agent
    - Uninstall agent from `vm -> Extentions + applications`
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

[1]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal#prerequisites
[2]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics#supported-operating-systems
[3]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview#supported-operating-systems
[4]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview
[5]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration
[6]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agents-overview#install-the-agent-and-configure-data-collection
[7]: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal#update
[8]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics
[9]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics#supported-operating-systems
[10]: https://learn.microsoft.com/en-us/troubleshoot/azure/virtual-machines/performance-diagnostics#install-and-run-performance-diagnostics-on-your-vm
[11]: https://learn.microsoft.com/en-us/azure/virtual-machines/extensions/oms-windows#extension-schema
[12]: https://learn.microsoft.com/en-us/azure/azure-monitor/vm/vminsights-enable-overview#migrate-from-log-analytics-agent-to-azure-monitor-agent
