# Netowrk Watcher

## Network Watcher Tools

1. **IP flow verify**: It allows you to detect traffic filtering issues at a virtual machine level.
2. **NSG diagnostics**: It helps you understand which network traffic is allowed or denied in your Azure virtual network along with detailed information for debugging.
3. **Next hop**: It helps you determine how a packet will get from one VM to any other.
4. **Effective security rules**: It displays all the effective NSG rules which are to be applied on the network interface.
5. **Connection troubleshoot**: It helps you diagnose VPN connectivity issues between your on-premises site and Azure.
6. **Packet capture**: It allows you to capture network traffic packets on a VM or virtual network subnet for analysis and troubleshooting.
7. **VPN troubleshoot**: It helps you diagnose VPN connectivity issues between your on-premises site and Azure.

Here are some examples of how these tools can be used:
- IP flow verify: You can use this tool to diagnose connectivity issues from or to the internet and from or to the on-premises environment, and look at the rules for all Network Security Groups (NSGs) applied to the network interface, such as a subnet or virtual machine NIC.
- NSG diagnostics: You can use this tool to verify that your network security group rules are set up properly.
- Next hop: You can use this tool to determine how a packet will get from one VM to any other.
- Effective security rules: You can use this tool to display all the effective NSG rules which are to be applied on the network interface.
- Connection troubleshoot: You can use this tool to diagnose VPN connectivity issues between your on-premises site and Azure.
- Packet capture: You can use this tool to monitor and diagnose networking issues without logging in to your virtual machines (VMs) using Network Watcher. Trigger packet capture by setting alerts, and gain access to real-time performance information at the packet level.
- VPN troubleshoot: You can use this tool to diagnose VPN connectivity issues between your on-premises site and Azure.

## [GH | ArtiomLK | Create an Azure Network Watcher Connection Monitor][1]

[1]: https://github.com/ArtiomLK/commands/blob/main/ps/readme.md#create-an-azure-network-watcher-connection-monitor