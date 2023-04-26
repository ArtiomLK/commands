# NSG Azure Diagnostic Settings

- Network Security Event:
  - Entries are logged for which NSG rules are applied to VMs, based on MAC address.

- Network Security Rule counter:
  - Contains entries for how many times each NSG rule is applied to deny or allow traffic. The status for these rules is collected every 300 seconds.

```KQL
AzureDiagnostics
| top 10 by TimeGenerated
```

## Additional Resources

- Network Watcher
- [MS | Learn | Resource logging for a network security group][1]

[1]: https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-nsg-manage-log
