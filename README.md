<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create and Associate NSGs
- Step 2: Define Security Rules
- Step 3: Test Traffic Between VMs
- Step 4: Monitor and Inspect Traffic


<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/XxAxjfD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To configure and manage traffic between Azure Virtual Machines using Network Security Groups (NSGs), you first create NSGs in the Azure portal. NSGs act as virtual firewalls that control inbound and outbound traffic at both the subnet and NIC (network interface) levels. Each NSG consists of security rules that define allowed or denied traffic based on parameters like source/destination IP address, port number, and protocol (TCP or UDP). Once created, you associate the NSG with the relevant subnet or VM network interface to begin enforcing the traffic rules.


</p>
<br />

<p>
<img src="https://i.imgur.com/HydtS0x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After applying Network Security Groups (NSGs), you define custom security rules to manage the traffic flow between virtual machines (VMs). For example, to allow communication between two VMs on TCP port 80 (HTTP), you create an inbound rule on the destination VM’s NSG to allow traffic from the source VM’s IP address or subnet. You can test and validate connectivity between VMs using PowerShell commands, such as Test-NetConnection, or tools like Telnet and Ping (if ICMP is allowed). Proper prioritization of rules is critical since NSGs evaluate rules in order of priority, with lower numbers having higher precedence.
</p>
<br />

<p>
<img src="https://i.imgur.com/mP2nRA1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To inspect and monitor traffic, you enable NSG Flow Logs using Azure Network Watcher. These logs provide detailed records of allowed and denied flows through your NSG rules. The logs are stored in a designated Azure Storage Account and can be analyzed using Azure tools like Traffic Analytics or Log Analytics Workspace to identify anomalies, performance issues, or security threats. This visibility helps ensure that your network is both secure and functioning as expected.
</p>
<br />
