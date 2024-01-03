<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial delineates the deployment of on-premises Active Directory on Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create the Domain Controller VM (Windows Server 2022)
- Create the Client VM (Windows 10)
- Ensure Connectivity between the client and Domain Controller
- Install Active Directory

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/YUBRHL8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DHyVlVC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/></p>
<p>
Establish a Domain Controller Virtual Machine (VM) titled "DC-1" utilizing Windows Server 2022, ensuring to note the corresponding Resource Group and VNet created. Configure the NIC's Private IP address as static. Subsequently, generate a Windows 10 Client VM named "Client-1" within the identical Resource Group and VNet. Verify their network association within the Network Watcher topology to confirm both VMs' presence on the same VNet.
</p>
<br />

<p>
<img src="https://i.imgur.com/MzTj3kV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0iCtbkz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
To resolve connectivity issues, you should start by logging in to Client-1. From there, you can use the "ping -t <ip address>" command to check the private IP of DC-1. If the ping test fails, you will need to enable ICMPv4 on the Windows Firewall of the Domain Controller. Once you've completed these steps, check back on Client-1 to confirm a successful ping.
</p>
<br />

<p>
<img src="https://i.imgur.com/0mUcZbx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wnOCGRE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 and install Active Directory Domain Services. Then promote it as a Domain Controller by setting up a new forest with mydomain.com.
</p>
<br />

<p>
<img src="https://i.imgur.com/Bzv6lKo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the virtual machine has finished restarting, please log back into DC-1 by using the username mydomain.com\labuser.
</p>
<br />
