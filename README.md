<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deploying Active Directory Part1 (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube/ClipChamp: How to Deploy Active Directory within Azure Part1](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Active Directory Domain Services were installed and configured on DC-1, promoting it to a Domain Controller with the domain mydomain.com.

- Two Organizational Units (OUs) were created: _EMPLOYEES and _ADMINS. A Domain Admin user (jane_admin) was set up and added to the Domain Admins group.

- Client-1 was successfully joined to the domain, and its organizational structure was updated by placing it into the _CLIENTS OU in ADUC.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Part 1: Install Active Directory

1.Login to DC-1: Log in to the server designated as DC-1.

2.Install Active Directory Domain Services: Use the Server Manager to add the Active Directory Domain Services (AD DS) role to the server.

3.Promote DC-1 to Domain Controller:

During the AD DS installation, you'll be prompted to promote the server to a domain controller.
Choose the option to set up a new forest and enter your domain name (e.g., mydomain.com).

4.Restart the Server: After the promotion is complete, restart the server to apply changes.

5.Login as User: After the server restarts, log back into DC-1 as the user mydomain.com\labuser.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Domain Admin User & Join Client-1 to the Domain

1.Create Organizational Units (OUs) in ADUC:

Open Active Directory Users and Computers (ADUC).
Create an Organizational Unit (OU) named _EMPLOYEES.
Create another OU named _ADMINS.

2.Create Domain Admin User:

Create a new employee account Jane Doe with the username jane_admin and set the password to Cyberlab123!.
Add jane_admin to the Domain Admins security group.

3.Login as jane_admin:

Log out from DC-1 and log back in as mydomain.com\jane_admin.
Use jane_admin as your admin account going forward.

4.Join Client-1 to the Domain:

Log in to Client-1 as the original local admin (labuser).
Join Client-1 to the domain mydomain.com (the computer will restart).
After the restart, log into the Domain Controller (DC-1) and verify that Client-1 appears in ADUC.

5.Organize Client-1 in ADUC:

Create a new OU called _CLIENTS in ADUC.
Drag Client-1 into the _CLIENTS OU.
</p>
<br />
