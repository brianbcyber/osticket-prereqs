<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine (Windows 10, 4 vCPUs)

- Remote Desktop Access

- Admin Privileges in the VM

<h2>Installation Steps</h2>

<p>
<img "Screenshot 2025-08-06 at 7 52 24 PM" src="https://github.com/user-attachments/assets/3cce93ea-7c5e-480f-afe3-474e1aca779c" />

</p>
<p>
1. Create Virtual Machine

Name: osticket-vm

Username: labuser

Password: osTicketPassword1!

Use Azure Portal to create the VM with Windows 10 and at least 4 vCPUs.
</p>
<br />

<img width="409" height="558" alt="Screenshot 2025-08-06 at 7 57 54 PM" src="https://github.com/user-attachments/assets/540adf37-5e4b-44ad-97c4-4909766f92a5" />

<p>

</p>
<p>
2. Connect to the VM
  
Use Remote Desktop (RDP) to log into the VM with the credentials provided.
</p>
<br />

<img width="1716" height="838" alt="image" src="https://github.com/user-attachments/assets/34f2ec6a-8907-438a-8a28-3e9454847ddd" />

<p>
</p>
<p>
3. Download and Extract Installation Files

  Download osTicket-Installation-Files.zip onto the VM.

  Extract to desktop. You should now see a folder named osTicket-Installation-Files.
</p>
<br />

<p>
  <img width="1644" height="992" alt="image" src="https://github.com/user-attachments/assets/698d87b3-d577-4333-99d4-9142334f8839" />

</p>
<p>
4. Install IIS with CGI Support

Open "Turn Windows features on or off".

Enable the following:

  Internet Information Services (IIS)

  World Wide Web Services → Application Development Features → CGI
</p>
<br />

<p>
<img width="1442" height="824" alt="image" src="https://github.com/user-attachments/assets/8bc921d4-c3a3-4cd7-92fa-0de01608a6a7" />

<img width="1366" height="808" alt="image" src="https://github.com/user-attachments/assets/b2d52927-53be-4182-ad6d-3fe823682459" />

<img width="1294" height="890" alt="image" src="https://github.com/user-attachments/assets/3b6e9b43-17d8-4e25-a8ec-f8f60b28717a" />



</p>
<p>
5.Install Required Components (From Installation Folder)

Install the following in order:

  PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

  IIS Rewrite Module (rewrite_amd64_en-US.msi)

  VC++ Redistributable (VC_redist.x86.exe)
</p>
<br />

<p>
  <img width="1042" height="874" alt="image" src="https://github.com/user-attachments/assets/77cdf932-6c1c-4cbf-b5b5-86b7cee9e306" />

</p>
<p>
6. Configure PHP

Create a folder: C:\PHP

Extract php-7.3.8-nts-Win32-VC15-x86.zip into C:\PHP
</p>
<br />

<p>
<img width="1254" height="954" alt="image" src="https://github.com/user-attachments/assets/6115f32d-fb6b-4ff1-abc5-de083cce1407" />

<img width="890" height="620" alt="image" src="https://github.com/user-attachments/assets/a1e19edd-a46c-4c64-bd66-f05acc91bb10" />

<img width="594" height="500" alt="image" src="https://github.com/user-attachments/assets/ab8d3b7d-14d3-4755-b6cf-19fae72352d1" />


</p>
<p>
7. Install MySQL 5.5
  
Run mysql-5.5.62-win32.msi

Choose Typical Setup

After installation, run MySQL Configuration Wizard:

  Select Standard Configuration

  Username: root

  Password: root
</p>
<br />

<p>
<img width="822" height="592" alt="image" src="https://github.com/user-attachments/assets/3dfdcf5b-c053-4d8a-91d8-3b31a5c237e0" />

<img width="1498" height="878" alt="image" src="https://github.com/user-attachments/assets/b79b9eaf-14e7-4758-a192-5d8bf3ed19a7" />

<img width="1530" height="896" alt="image" src="https://github.com/user-attachments/assets/4946976d-fd59-40f8-9a53-c870df22edf7" />


</p>
<p>
8.  Register PHP in IIS

Open IIS Manager as Administrator

Click on PHP Manager

Register: C:\PHP\php-cgi.exe

Restart IIS (Stop & Start the server)
</p>
<br />

<p>
<img width="1266" height="726" alt="image" src="https://github.com/user-attachments/assets/e3b58a23-c69b-4dbd-8be9-e24827ead94f" />

<img width="1512" height="840" alt="image" src="https://github.com/user-attachments/assets/d8509677-3160-43ac-a606-667e41b3c051" />

<img width="746" height="596" alt="image" src="https://github.com/user-attachments/assets/216d7b5f-6bb6-4ec6-9e5d-c152e9fa86d5" />



</p>
<p>
9.  Install osTicket
  
Extract osTicket-v1.15.8.zip

Copy the upload folder to: C:\inetpub\wwwroot

Rename upload to osTicket

Restart IIS
</p>
<br />

<p>
<img width="866" height="832" alt="image" src="https://github.com/user-attachments/assets/ef2aabe2-20e6-44da-8b09-136ea35753f2" />

</p>
<p>
10. Browse to osTicket
  
  In IIS: Sites → Default Web Site → osTicket

  Click *Browse :80

You’ll see the osTicket setup page with some missing PHP extensions.
</p>
<br />

<p>
<img width="1228" height="654" alt="image" src="https://github.com/user-attachments/assets/565933b0-1593-4ff7-bdcc-41918015b6e0" />

</p>
<p>
11. Enable PHP Extensions

In PHP Manager:

Enable the following:

  php_imap.dll

  php_intl.dll

  php_opcache.dll

Refresh the browser.

</p>
<br />

<p>
<img width="924" height="626" alt="image" src="https://github.com/user-attachments/assets/b9a8afc0-5565-4d4d-92db-afb2c72e7c13" />

</p>
<p>
12. Rename Config File
  
Rename file:
  
  From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php  
  To:   C:\inetpub\wwwroot\osTicket\include\ost-config.php

  

</p>
<br />

<p>
<img width="1030" height="708" alt="image" src="https://github.com/user-attachments/assets/a3312410-696b-40d5-8467-3f564555c193" />

</p>
<p>
13. Set File Permissions

Right-click ost-config.php → Properties → Security

Disable inheritance → Remove all

Add new permission:

User: Everyone

Permissions: Full control
</p>
<br />

<p>
<img width="864" height="452" alt="image" src="https://github.com/user-attachments/assets/92fad509-bf70-4938-8155-49d40e45b7b5" />

</p>
<p>
14. Continue osTicket Web Setup

In your browser:

Helpdesk Name: (your choice)

Default Email: (support@yourdomain.com)
</p>
<br />

<img width="806" height="556" alt="image" src="https://github.com/user-attachments/assets/bdadeb89-1814-49c8-af3b-67a537dfd781" />

<img width="1002" height="638" alt="image" src="https://github.com/user-attachments/assets/06c24a66-b772-4cc8-83be-1b2cd33b27df" />


<p>
installation.
</p>
<p>
15. Install HeidiSQL & Configure Database
  
Install HeidiSQL from the installation folder

Open HeidiSQL and connect using:

Username: root

Password: root

Create a database called: osTicket
</p>
<br />

<p>
<img width="604" height="398" alt="image" src="https://github.com/user-attachments/assets/56408f13-43a8-4a29-92fd-e80e88c3c34b" />

<img width="898" height="704" alt="image" src="https://github.com/user-attachments/assets/9954fae7-7c3d-470f-b1a9-02caa55dda7e" />


</p>
<p>
16. Complete osTicket Setup

In the osTicket web setup page:

Database Name: osTicket

MySQL Username: root

MySQL Password: root

Click Install Now!
</p>
<br />

<p>
<img width="870" height="454" alt="image" src="https://github.com/user-attachments/assets/ea122339-7941-489d-82e9-7586bbca6a2a" />

<img width="540" height="554" alt="image" src="https://github.com/user-attachments/assets/4461a2a8-f12d-47c3-80bf-669dd67aa9c1" />

<img width="1164" height="568" alt="image" src="https://github.com/user-attachments/assets/444f7b1d-00d4-4db8-8c90-2bbf1910946d" />



</p>
<p>
17. Access osTicket
  
Admin Panel: http://localhost/osTicket/scp/login.php

End-User Portal: http://localhost/osTicket/
</p>
<br />
