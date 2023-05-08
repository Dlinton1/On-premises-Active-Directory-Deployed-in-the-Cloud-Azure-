<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

<p>
Set up Azure resources.
<p>
<img src="https://i.imgur.com/VrnWfp0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This step involved the creation of two Virtual Machines; one named DC1, which serves as the domain controller, and the other named client1.
</p>
<br />

<p>
Verify the connection between the two VMs.
<p>
<img src="https://i.imgur.com/TCFi4u1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/JAInfOY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<p>
<img src="https://i.imgur.com/1RtrcPH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
Ensuring that both VMs can communicate with each other is a critical step. Initially, when I tested the connection using the "ping -t" command, it failed and returned a "request timed out" response. To resolve this issue, I enabled the ICMPv4 protocol in the local Windows firewall. After making this change, I tested the connection again with the "ping -t" command, and this time it was successful. The command returned a reply.
</p>
<br />

<p>
Install the Active Directory service.
<p>
<img src="https://i.imgur.com/cl8gdBD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/1CNKA1K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To proceed, install Active Directory Domain Services and set up a new forest with the domain name "mydomain.com".
</p>
<br />

<p>
Creating an administrator and a regular user account in Active Directory
<p>
<img src="https://i.imgur.com/djfY8bV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I added a user named Jane Doe to the ADMINS group in Active Directory.
</p>
<br />

<p>
Join the client1 VM to the mydomain.com domain.
<p>
<img src="https://i.imgur.com/H5PxIMS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
<img src="https://i.imgur.com/GAkNG1F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I configured the DNS settings for Client1 in the Azure portal to point to the private IP address of the DC.
</p>
<br />

<p>
Configure Remote Desktop access for non-admin users on Client1.
<p>
<img src="https://i.imgur.com/uNykIm6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />

<p>
Generate a database of users by creating multiple additional user accounts.
<p>
<img src="https://i.imgur.com/BSPCZYM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
A script was utilized to create 10,000 randomly named users, which enabled the creation of a comprehensive user database.
</p>
<br />
