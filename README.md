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

<h2>High-Level Deployment and Configuration Steps</h2>

- Creat 2 virtual machines on Azure and connect to them via remote desktop
- Install AD and promote to a DC on the server VM
- Connect the windows VM to the Domain Controller
- Use Powershell to populate the employee OU on the DC with the names of as many as they are

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/15gmCrm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is the process of installing Active Directory and promoting it to a Domain Controller
</p>
<br />

<p>
<img src="https://i.imgur.com/sDUDjXn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After linking both VM's by making the private ip of the Domain Controller the dns server of the windows machine, you connect them from the windows VM
</p>
<br />

<p>
<img src="https://i.imgur.com/vQKvMFi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
And finally, you populate the employee list with their names from Powershell ISE on the Domain Controller, after remotely allowing domain users to access the computer from the windows VM.
</p>
<br />
