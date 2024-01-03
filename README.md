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
<img src="https://i.imgur.com/fKRaoFW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/LEHOymx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/></p>
<p>
Establish a Domain Controller Virtual Machine (VM) titled "DC-1" utilizing Windows Server 2022, ensuring to note the corresponding Resource Group and VNet created. Configure the NIC's Private IP address as static. Subsequently, generate a Windows 10 Client VM named "Client-1" within the identical Resource Group and VNet. Verify their network association within the Network Watcher topology to confirm both VMs' presence on the same VNet.
</p>
<br />

<p>
<img src="https://i.imgur.com/lpal53A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/PkUCqnc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2SHj6Bz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
To troubleshoot connectivity concerns, begin by logging into Client-1. Execute the "ping -t " command from Client-1 to examine the private IP of DC-1. In case the ping test fails, consider enabling ICMPv4 within the Windows Firewall settings of the Domain Controller. Subsequently, reattempt the ping from Client-1 to validate a successful connection after implementing these adjustments.
</p>
<br />

<p>
<img src="https://i.imgur.com/ExuDg71.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/g8fsIoh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/hSfDXrS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Access DC-1 and proceed with the installation of Active Directory Domain Services. Subsequently, initiate the promotion process to establish it as a Domain Controller by configuring a new forest named mydomain.com.
</p>
<br />

<p>
<img src="https://i.imgur.com/hFUEhqH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Following the virtual machine's completion of the restart, I log in again to DC-1 using the username sbmusic.com\labuser.
</p>
<br />
