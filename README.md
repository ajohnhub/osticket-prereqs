<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This walkthrough outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
Create a resource group and title it "osTicket". Afterwards create a VM with 2-4 CPUs. In this example I will be using 4 CPUs.
  
 <img src="https://github.com/user-attachments/assets/b2da39eb-c374-429a-a787-3da45e11fdf7" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>Next, connect to your newly created VM using RDP with the public IPv4 address.
</p>
<img src="https://github.com/user-attachments/assets/b24b938b-51a8-4141-bbc7-c962d7d40188" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>
Once you are connected to your VM, you will need to enable IIS. Access the control panel, then select Uninstall a program. Next, select "Turn Windows features on or off". A list will appear, and then you will enable Internet Information Services.
</p>  
<img src="https://github.com/user-attachments/assets/53c1dce3-0105-4db5-bb19-de1a6d19273f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
</p>
<p>
The link below includes the download to install osTicket.
https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<img src="https://github.com/user-attachments/assets/289288ae-653e-4c50-afa1-2cbec8eb5e2d" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
After the Web Installer Platform is installed, open it. From inside the application, you are going to install MySQL 5.5. and then install the x86 version of PHP up to 7.3 afterwards. 
</p>
<img src="https://github.com/user-attachments/assets/06a0deff-48bb-4784-b2fc-df390dc0c1a8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
Now, download osTicket. Then, extract and copy the "upload" folder into C:\inetpub\wwwroot. Rename the folder to osTicket.
</P>
<img src="https://github.com/user-attachments/assets/eb885747-879a-4d64-8546-8758cb20155f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/7652d3dc-9182-43c9-bb98-99c96c2902f9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>
Open IIS Manager and restart the server. Once inside IIS manager, navigate to Sites->Default->osTicket on the right, click "Browse*.80" from there your default browser. The osTicket web server should have opened.
</p>
<img src="https://github.com/user-attachments/assets/921b4cb6-a438-4346-b8f6-599ad60ca0c8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/cf1777f6-193f-46a9-bf31-f45d60646a26" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Go back into the IIS manager and enable some extensions. Go to Sites->Default->osTicket
Then double click on PHP Manager. Click on "Disable or enable an extension", Enable "php_intl.dll" & "php_opcache.dll", then refresh the osTicket webserver and observe the changes. "Intl Extension" should now be enabled. 
</p>
<img src="https://github.com/user-attachments/assets/0f986d6d-9507-4d91-b06f-fe5f131adf02" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Go back into c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php rename the file to c:\inetpub\wwwroot\osTicket\include\ost-config.php
Assign permissions to ost-config.php. Disable inheritance-> Remove all
New Permissions->Everyone->all
</p>
<img src="https://github.com/user-attachments/assets/09274f2a-48e5-4567-879c-ce1c98da648e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/0391b94a-df3a-4e49-baf7-19b2edc790cb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Assign permissions to ost-config.php. Disable inheritance-> Remove all
New Permissions->Everyone->all
</p>
<img src="https://github.com/user-attachments/assets/db1b13bd-1c28-41fe-99c0-cacbda11aaea" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<p>Continue Setting up osticket in the browser MySQL Database: osTicket MySQL Username: root MySQL Password: Password1 Click “Install Now!”
Congratulations, hopefully it is installed with no errors!
Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)
