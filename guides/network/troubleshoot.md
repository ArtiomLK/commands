# Troubleshoot Network Connectivity

## [Test-NetConnection][1] from Windows VMs

```PowerShell
# 10.10.10.1 is the remote IP
Test-NetConnection 10.10.10.1 -Port 3389 -InformationLevel "Detailed"
```

## [GH | ArtiomLK | Use Azure Network Watcher Connection Monitor][3]

## Additional Resources

- Network
- [MS | Learn | Test-NetConnection][1]
- [MS | Learn | What address ranges can I use in my VNets?][2]
- Network Watcher
- [MS | Learn | What is Azure Network Watcher?][4]

[1]: https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection
[2]: https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-faq#what-address-ranges-can-i-use-in-my-vnets
[3]: ./nw/nw.md
[4]: https://learn.microsoft.com/en-us/azure/network-watcher/network-watcher-monitoring-overview