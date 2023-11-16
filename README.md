<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Lab</h1>
This lab showcases the setup and usage of Active Directory in a Microsoft Azure Virtual Machine.<br />


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
<img src="https://i.imgur.com/0ErUDHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setup two virtual machines. One running Windows Server 2022 (DC-1) and the other running Windows 10 (Client-1). Set DC-1's NIC private IP address to be static. Use the same resource group and make sure that the Client-1 uses the same Vnet as DC-1.
</p>
<br />

<p>
<img src="https://i.imgur.com/18TH1ft.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 and install Active Directory Domain Services.
</p>
<br />

<p>
<img src="https://i.imgur.com/0rVRRov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setup a new forest as mydomain.com. Restart and then log back into DC-1.
</p>
<br />

<p>
<img src="https://i.imgur.com/18TH1ft.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers, create two Organizational Units named "_EMPLOYEES" and "_ADMINS". Create a new employee named “Jane Doe” and add them to the "Domain Admins" security group. Log out of DC-1 and log back in as "Jane Doe". 
</p>
<br />

<p>
<img src="https://i.imgur.com/J1BS153.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Azure Portal, set Client-1’s DNS settings to the DC-1’s Private IP address and restart Client-1. Login to Client-1 and join it to the domain. 
</p>
<br />

<p>
<img src="https://i.imgur.com/18TH1ft.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers, create two Organizational Units named "_EMPLOYEES" and "_ADMINS". Create a new employee named “Jane Doe” and add them to the "Domain Admins" security group. Log out of DC-1 and log back in as "Jane Doe". Log into Client-1 as "Jane Doe and open system properties. Next click "Remote Desktop" and allow “domain users” access to remote desktop. You can now log into Client-1 as a non-administrative user. 
</p>
<br />

<p>
<img src="https://i.imgur.com/JXBwafw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to DC-1 as "Jane Doe" and open PowerShell_ise as an administrator. Paste the script from, (https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) and run it. Observe the accounts being created. Attempt to login into Client-1 with one of the newly created accounts.
</p>
<br />
