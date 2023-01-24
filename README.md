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


<h2>Actions and Observations</h2>

First, we'll need to create two VMs using Azure. One running Windows 10 and the other running Ubuntu. When creating them, make sure they are both on the same Vnet. After that, we can check the Network Watcher and observe that both VMs are on the same network. 
<p>
<img src="https://imgur.com/LnJEKd8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

Next, connect to VM1 using RDP. Go to this link: https://www.wireshark.org/download.html and download Wireshark onto VM1. We'll be using this to inspect network traffic between the two VMs. Once downloaded, click Ethernet and then click "start capturing packets". Observe the traffic. 
<p>
<img src="https://imgur.com/Bk8wNL5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

Moving on, we're now going to filter the packet capture to show only ICMP traffic. Type "icmp" in the filter bar. ICMP is a protocol that is used by network devices to communicate connection issues. We're going to ping VM2 from VM1 by obtaining VM2's private IP address. This can be found on the azure portal. Open the command prompt on VM1 and type, "ping" and then VM2's private IP address. Observe the traffic on Wireshark.
<p>
<img src="https://imgur.com/yWNw2Ep.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://imgur.com/LDliLWc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<br />

Next, initiate a perpetual ping between VM1 and VM2 by typing "ping x.x.x.x -t". Once thats going, we are going to change the firewall settings on VM2 to block ICMP traffic. Search "Network Security Groups" on the Azure portal and choose VM2. Then click "Inbound security rules" and then add the rule. Observe the traffic and notice that the request timed out and on Wireshark, it shows that no response was found.
<p>
<img src="https://imgur.com/LTEOIuf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://imgur.com/sgcyX21.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
