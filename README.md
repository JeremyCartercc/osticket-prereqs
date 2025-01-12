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

- Download the osTicket-Installation-Files.zip and unzip it onto your desktop.
- Install / Enable IIS in Windows WITH CGI
  
<h2>Installation Steps</h2>

<p>
<h2>1. Install PHP Manager for IIS and install the Rewrite module</h2>
 
  ![image](https://github.com/user-attachments/assets/7a853722-8bd9-46d3-9493-4a98363999c4)

</p>
<p>
Double click PHP Manager Installer and click Next, Next and then finish, do the same for Rewrite Module.
</p>
<br />

<p>
<h2>2. Create the directory C:\PHP and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder</h2>

  ![image](https://github.com/user-attachments/assets/99d2fb14-25a7-4aec-9823-54ebaaaa5ea5)

</p>
<p>
Navigate to C Drive folder, File Explorer > This PC > Windows (C:) and create a new folder called PHP, go back to the osTicket Installation file and unzip PHP 7.3.8 into the new PHP folder you just created.
</p>
<br />

<p>
<h2>3. Install VC_redist.x86.exe and MySQL 5.5.62, then configure MySQL</h2>

  ![image](https://github.com/user-attachments/assets/0aaf7eef-76ee-41ae-bfad-6996a5bbb87a)

</p>
<p>
Double click both and install as normal, choose typical setup for MySQL. Once you finish installing MySQL launch the Server Instance Configuration Wizard. Click next and then choose standard configuration, click next 2x and then set your root password. Hit next and then Execute and Finish.
</p>
<br />

<p>
<h2>4. Register PHP from within ISS and install OsTicket</h2>

 ![image](https://github.com/user-attachments/assets/c4a98236-731f-4e13-8674-8a2f1b384d5b)


</p>
<p>
Click start and search up ISS, run as admin. Open PHP manager and press "Register new PHP version", browse to PHP folder in C drive and double click PHP.CGI and press ok. Reload ISS (Stop and Start the server). Now we will install OsTicket, extract Os-Ticket from installation file. Copy upload folder to “c:\inetpub\wwwroot”, Rename “upload” to “osTicket” and restart the ISS server.
</p>
<br />

<p>
<h2>5. Enable some extensions on osTicket</h2>

 ![image](https://github.com/user-attachments/assets/d74c9416-7889-40e1-b122-fd882d4306b6)


</p>
<p>
Go to ISS and press Sites > Default Web Site > osTicket > PHP Manager. Click “Enable or disable an extension” and enable php_imap.dll, php_intl.dll, and php_opcache.dll.

</p>
<br />

<p>
<h2>6. Rename and install permission to ost-config.php</h2>

  ![image](https://github.com/user-attachments/assets/a5c08fdc-e749-42b3-8090-1d5b44765017)


</p>
<p>
Open file explorer and browse to C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php. Right clock ost-config.php and go to properties, click security and then Advanced. Click Disable Inheritance and remove all inherited permissions. Press Add and then Principal and put Everyone, press ok and then Full Control.
</p>
<br />

<p>
<h2>7. Continue setting up osTicket in the browser</h2>

  ![image](https://github.com/user-attachments/assets/b7a99229-4854-4fe8-91f9-a4a6a4de5d34)


</p>
<p>
Press continue and put in your information, the default email and admin user email must be different. Once you get to database settings move on to step 8 and after that come back here. After completing step 8, put osTicket in MySQL database and enter your username and password created in step 3 and press install now. That's it, osTicket is now installed!
</p>
<br />

<p>
<h2>8. From the “osTicket-Installation-Files” folder, install HeidiSQL</h2>

 ![image](https://github.com/user-attachments/assets/caccc74f-2caa-44f9-9f71-c4847faa8dfb)


</p>
<p>
Double click HeidiSQL installer, keep clicking next and then install. Once you finish it should automatically open and you'll want to press skip and then New. Put in the password you created for the MySQl Server in Step 3 and press Open. Now we want to create a database names "osTicket" so right click the unamed drop down menu on the left in the image go to create new and then database. You must name it exactly osTicket. Go back and finish step 7 and then you're done!
</p>
<br />
