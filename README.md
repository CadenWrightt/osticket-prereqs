<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS
- the Rewrite Module
- VC_redist.x86.exe
- MySQL 5.5.62
- HeidiSQL.

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/850c49b8-ef49-40ee-ac3a-48ecd1e1763c)


<p>
</p>
<p>
First, create a virtual machine in azure make sure it's windows 10 with 4 vCPUs, Create a Name, Username, and a Password then log into the VM with Remote Desktop.
</p>
<br />

<p>

  ![image](https://github.com/user-attachments/assets/20be8764-96fd-41c1-9331-22e49cb82c06)
  
Within the osTicket virtual machine download osTicket-Installation-Files.zip and unzip it onto your desktop | install / enable IIS in Windows with CGI | From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) | From the same folder, install the Rewrite Module (rewrite_amd64_en-US.msi) | 

![image](https://github.com/user-attachments/assets/38477c6d-8761-40ef-a20c-b3e9465fc8b0)

</p>
<p>
Create the directory C:\PHP | From the same folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder | From the same osTicket folder, install VC_redist.x86.exe. | From the “osTicket-Installation-Files” folder install MySQL 5.5.62, Launch Configuration Wizard (after install) Standard Configuration | Username: root Password: root, then open IIS as an admin

</p>
<br />

<p>

  ![Screenshot 2024-12-06 100258](https://github.com/user-attachments/assets/da029ee5-73c7-4421-932e-3c582559e376)

  Register PHP from within IIS | Reload IIS (Open IIS, Stop and Start the server) | Install osTicket v1.15.8, From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”, Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket” | Reload IIS (Open IIS, Stop and Start the server) | 

![Screenshot 2024-12-06 100802](https://github.com/user-attachments/assets/6bd1fbfb-fa35-4332-98e5-da56305f77fc)

On the right, click “Browse *:80”, Note that some extensions are not enabled, Click “Enable or disable an extension", Enable: php_imap.dll, Enable: php_intl.dll, Enable: php_opcache.dll, Refresh the osTicket site in your browser, observe the changes |

![Screenshot 2024-12-06 100938](https://github.com/user-attachments/assets/41e09cd1-01dd-49de-a802-90dfcbbbd413)

Rename: ost-config.php From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, To: C:\inetpub\wwwroot\osTicket\include\ost-config.php | 

![Screenshot 2024-12-06 101204](https://github.com/user-attachments/assets/d3395c0d-b843-4aef-a28a-9a37e0d674df)

</p>
<p>
Assign Permissions: ost-config.php, Disable inheritance -> Remove All, New Permissions -> Everyone -> All
</p>
<br />

![Screenshot 2024-12-06 101604](https://github.com/user-attachments/assets/f9b6390e-f434-4305-9f0b-2c2917e06b6c)

Continue Setting up osTicket in the browser (click Continue) | From the “osTicket-Installation-Files” folder, install HeidiSQL, Open Heidi SQL, Create a new session, root/root, Connect to the session, 

![Screenshot 2024-12-06 101956](https://github.com/user-attachments/assets/16776809-23aa-4896-90bc-f929e4a8d9b2)


<p>
</p>
<p>
Create a database called “osTicket” | Continue Setting up osTicket in the browser, MySQL Database: osTicket, MySQL Username: root, MySQL Password: root, Click “Install Now!”
</p>
<br />

<p>

 ![Screenshot 2024-12-06 101909](https://github.com/user-attachments/assets/82a61a65-966f-4338-ad5f-c245c97b2de2)



</p>
<p>
Congratulations, hopefully it is installed with no errors!

</p>
<br />
