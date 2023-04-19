# Troubleshoot Network Connectivity

## [Test-NetConnection][1] from Windows VMs

```PowerShell
# 10.10.10.1 is the remote IP
Test-NetConnection 10.10.10.1 -Port 3389 -InformationLevel "Detailed"
```

## Additional Resources

- Monitoring
- [MS | Learn | Test-NetConnection][1]

[1]: https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection
