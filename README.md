# osticket-prereqs

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers the requirements and installation process for the open-source help desk ticketing system, osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b>

<h2>List of Prerequisites</h2>

- Azure Virtual Machine 
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p> <img width="1531" height="851" alt="image" src="https://github.com/user-attachments/assets/34b8f8a2-f7b4-468e-a609-5e616ce38fdb" />

</p>
<p>
Create an Azure resource group named “osTicket,” then deploy a virtual machine within that group. The VM should use the Windows 10 Pro image and be configured with a minimum of 2 vCPUs. This virtual machine will be used as a practice environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/H2B3g7x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, connect to the virtual machine using Remote Desktop Protocol (RDP). Locate and copy the VM’s Public IPv4 address from the Azure portal, then use that address to initiate the RDP session.
</p>
<br />

<p>
<img src="https://i.imgur.com/2VqhhFo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After connecting to the VM, enable IIS by opening Control Panel and selecting “Turn Windows features on or off.” In the list that appears, scroll down to “Internet Information Services (IIS)” and check the box to install and activate it.</p>
<br />

<p>
<img src="https://i.imgur.com/jdy6kVT.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
[https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD Next, use the provided download link to retrieve all required files for installing and launching osTicket. After downloading, open the osTicket Installation folder and run the PHP Manager installer to continue with the setup process.
</p>
</p>
<br />

<p>
<img src="https://i.imgur.com/BraQ2Sp.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the same folder, run the installer for the Rewrite Module to continue configuring the environment.</p>
<br />

<p>
<img src="https://i.imgur.com/3G7QEou.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BJ7pQXn.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new directory at C:\PHP. Then unzip the PHP 7.3.8 file (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all of its contents into the C:\PHP folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/vnapOUJ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install the VC_redist.x86.exe file from the osTicket Installation folder to ensure the required Visual C++ Redistributable components are properly installed.
</p>
<br />

<p>
<img src="https://i.imgur.com/6Ni4PkJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to configure the MySQL database server.
</p>
<br />

<p>
<img src="https://i.imgur.com/HFBKqHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS Manager with administrative privileges and register PHP by configuring the required settings. Once completed, restart the IIS server by selecting the Restart option within IIS Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/dUEDOI2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the upload folder into C:\inetpub\wwwroot. Then, inside C:\inetpub\wwwroot, rename the upload folder to osTicket.

</p>
<br />

<p>
<img src="https://i.imgur.com/ofoOo0Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to IIS Manager and restart the server. Then, enable the required PHP extensions by navigating to Sites → Default → osTicket and opening PHP Manager. Choose “Disable or enable an extension” and enable php_intl.dll, php_opcache.dll, and php_imap.dll. After enabling them, refresh the osTicket web server and confirm that the Intl extension is now active.
</p>
<br />

<p>
<img src="https://i.imgur.com/JEdBG6b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to C:\inetpub\wwwroot\osTicket\include and locate the file named ost-sampleconfig.php. Rename this file to ost-config.php while keeping it in the same directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/vFIs9DL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set the correct permissions for the ost-config.php file by right-clicking it and selecting Properties. Under the Security tab, turn off inheritance and remove all existing permission entries. Then, add the Everyone group and grant it full access.
</p>
<br />

<p>
<img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, complete the osTicket setup in your web browser by selecting Continue. Choose a name for your helpdesk and set a default email address to receive incoming ticket notifications from customers.
</p>
<br />
