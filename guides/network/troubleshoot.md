# Troubleshoot Network Connectivity

## [Test-NetConnection][1] from Windows VMs

```PowerShell
# 10.10.10.1 is the remote IP
Test-NetConnection 10.10.10.1 -Port 3389 -InformationLevel "Detailed"
```

## [Use Azure Network Watcher Connection Monitor to test connectivity][3]

## Additional Resources

- Network
- [MS | Learn | Test-NetConnection][1]
- [MS | Learn | What address ranges can I use in my VNets?][2]

[1]: https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection
[2]: https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-faq#what-address-ranges-can-i-use-in-my-vnets
[3]: https://github.com/ArtiomLK/commands/blob/main/ps/readme.md#create-an-azure-network-watcher-connection-monitor
