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

- Enable IIS with CGI
- Install PHP Manager for IIS
- Install URL Rewrite Module
- Install PHP 7.3.8
- Install Microsoft Visual C++ Redistributable (x86)
- Install MySQL Server
- Download and extract osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/RqRQhWm.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create your virtual machine that will run osTicket. Launch and log into the system.
</p>
<br />

<p>
<img src="https://i.imgur.com/OPDVCFd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Prepare IIS and PHP for osTicket

1. Open the "Turn Windows features on or off" utility.
2. Enable Internet Information Services (IIS) and make sure the CGI feature is also selected. This allows PHP to run within IIS.
3. After IIS is enabled, download and install the following:
   - PHP Manager for IIS – to easily manage PHP configurations.
   - URL Rewrite Module – to handle friendly URL routing for web applications.
4. Create the directory `C:\PHP`
5. Download PHP 7.3.8 and extract the files to the directory `C:\PHP`.
6. Once extracted, use **PHP Manager** to register the PHP installation with IIS.

At this point, IIS is fully configured to run PHP scripts, and you're ready to continue setting up osTicket.

</p>
<br />

<p>
<img src="https://i.imgur.com/AtL8O9M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To make sure PHP and MySQL work correctly, install the Microsoft Visual C++ Redistributable (x86). This is a required support file that helps both programs run on Windows.
</p>
<br />

<p>
<img src="https://i.imgur.com/Lpaxi3b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and run the MySQL Installer. During the setup, you’ll be asked to create a username and password. You’ll need these login details later to create the osTicket database and connect to it during the web-based installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/GdzrIew.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Run IIS as Administrator.

Use PHP Manager to register PHP by selecting the path:
`C:\PHP\php-cgi.exe`.

Then, restart IIS by stopping and starting the server to apply the changes.

<br />

<p>
<img src="https://i.imgur.com/DQEjiOV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To install osTicket in IIS, start by unzipping the `osTicket-v1.15.8.zip` file. Move the "upload" folder into `C:\inetpub\wwwroot` and rename it to "osTicket".

Next, open **IIS**, select the osTicket site, and use **PHP Manager** to enable the required PHP extensions:

* `php_imap.dll`
* `php_intl.dll`
* `php_opcache.dll`

Then, navigate to the `include` folder inside osTicket and rename the file `ost-config.php.dist` to `ost-config.php`.

Finally, adjust the file's permissions:

* Right-click the file, go to Properties > Security.
* Disable inheritance and give Everyone full control.

This allows osTicket to complete the setup during the web-based installation.

</p>
<br />

<p>
<img src="https://i.imgur.com/oJg2JuB.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Launch the osTicket Setup Page

1. Open a web browser.
2. Navigate to:  
   `http://localhost/osTicket`
3. Fill in the required helpdesk information (e.g., helpdesk name, default email, etc.).

Create the osTicket Database

1. Launch HeidiSQL (located where you extracted the osTicket files).
2. Connect using your MySQL login credentials.
3. Right-click your MySQL connection and select Create new → Database.
4. Name the new database:  
   `osTicket`

Complete the Installation

1. Return to the osTicket setup page in your browser.
2. Enter the database name and MySQL credentials when prompted.
3. Click “Install Now” to complete the setup.


</p>
<br />

<h2>Project Summary</h2>

This project demonstrates the complete deployment of the osTicket help desk system on a Windows 10 VM in Microsoft Azure, showcasing hands-on experience with:

Azure Virtual Machines for cloud-based infrastructure

Internet Information Services (IIS) for web hosting

PHP & PHP Manager setup and configuration

MySQL installation and database integration

HeidiSQL for GUI-based database management

osTicket deployment and troubleshooting

The process includes configuring web server environments, managing PHP dependencies, setting up databases, and completing a web-based application installation—demonstrating practical infrastructure and system administration skills within a cloud environment.
