# NSG Azure Diagnostic Settings

- Network Security Event:
  - Entries are logged for which NSG rules are applied to VMs, based on MAC address.

- Network Security Rule counter:
  - Contains entries for how many times each NSG rule is applied to deny or allow traffic. The status for these rules is collected every 300 seconds.

## Additional Resources

- Network Watcher
- [MS | Learn | Network Security Groups connector for Microsoft Sentinel][1]

[1]: https://learn.microsoft.com/en-us/azure/sentinel/data-connectors/network-security-groups