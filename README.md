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

- Create Resource Group and Virtual Machine in Microsoft Azure
- Install/Enable Internet Information Services (IIS) in Windows with CGI  
- Download and Install PHP Manager for IIS and Rewrite Module
- Create folder in directory for PHP & Download and Unzip PHP 7.3.8 files
- Download and Intsall VC file and MySQL
- Register PHP in IIS and reload to install osTicket v1.15.8
- Enable required extensions to continue installation of osTicket
- Install HeidiSQL to link MySQL database to osTicket

<h2>Installation Steps</h2>

<h2>Create Resource Group and Virtual Machine in Microsoft Azure</h2>
<p>
<img src="https://i.imgur.com/UgsgG1u.png"/>
</p>
<p>
Start by creating a resource group. Once you have the resource group created, create a virtual machine within the resource group. Make sure you give your virtual machine a Windows 10 (21H2) OS and set the region to be the same as the resource group's. Additionally, you want to be sure that the size of virtual machines is set to Standard_D4s_v3-4vcpus with 16 GiB of memory to provide optimal performance. Lastly, be sure to create a username and password for your virtual machine. 
</p>
<br />
<h2>Install/Enable Internet Information Services (IIS) in Windows with CGI</h2>
<p>
<img src="https://i.imgur.com/nJ9mIUX.png"/>
</p>
<p>
First, enter the public IP address in the Remote Desktop Connection window. Once connected, you will need to login to the virtual machine with your username and password. Once logged in, open the Control Panel and navigate to the Programs section. Within Programs, select the option to "Turn Windows features on or off". In the "Turn Windows features on or off" window, select all the highlighted options in the picture shown above to enable CGI. After selecting the options, click on the OK button to apply the changes.
</p>
<br />
<h2>Download and Install PHP Manager for IIS and Rewrite Module</h2>
<p>
<img src="https://i.imgur.com/POQFs99.png"/>
</p>
<p>
<img src="https://i.imgur.com/3CCvfIf.png"/>
</p>
<p>
Download and install PHP Manager and the Rewrite Module on the virtual machine.
</p>
<br/>
<h2>Create folder in directory for PHP & Download and Unzip PHP 7.3.8 files</h2>
<p>
<img src="https://i.imgur.com/bCAWNsz.png"/>
</p>
<p>
After downloading the PHP files, extract all of them into the PHP folder in Windows directory C:.
</p>
<br />
<h2>Download and Intsall VC file and MySQL</h2>
<p>
<img src="https://i.imgur.com/C2wPsdE.png"/>
</p>
<p>
<img src="https://i.imgur.com/wWZ8Env.png"/>
</p>
<p>
<img src="https://i.imgur.com/65oSix6.png"/>
</p>
<p>
When installing MySQL, make sure to select the "Typical Setup" option. Also, be sure to check the box for Launch Configuration Wizard (after install) before pressing the "Finish" button. In the Configuration Wizard, select "Standard Configuration" and install as a Windows service. Next, create a password for MySQL.  
</p>
<br />

<h2>Open IIS as an Administrator, Register PHP in IIS, and Restart IIS Server</h2> 
<p>
<img src="https://i.imgur.com/E7570UW.png"/>
</p>
<p>
<img src="https://i.imgur.com/Iy1msZE.png"/>
</p>
<p>
<img src="https://i.imgur.com/fqmRAoR.png"/>
</p>
<p>
In the windows start menu search "IIS" and select "Run as administrator". In IIS Manager, open PHP Manager and register new PHP version. Go to the PHP folder in the Windows C: directory and open the "php-cgi" folder. Next, restart the IIS server.
</p>
<br />

<h2>Install osTicket</h2>
<p>
<img src="https://i.imgur.com/UE7qfJQ.png"/>
</p>
<p>
After installing osTicket, copy the "upload" folder to C:\inetpub\wwwroot. (This can be done by dragging and dropping the "upload" folder.) In C:\inetpub\wwwroot, rename the "upload" folder "osTicket".
</p>
<br />

<h2>Reload IIS and Browse to *:80 to review what extensions need to be enabled</h2>
<p>
<img src="https://i.imgur.com/6x3wdFi.png"/>
</p>
<p>
In IIS go to Sites, Default, and osTicket. Next, click on "Browse *:80" to open osTicket in a web browser.
</p>
<br />

<h2>Enable extensions in IIS</h2>
<p>
<img src="https://i.imgur.com/w4WcFla.png"/>
</p>
<p>
In IIS go to Sites, Default, and osTicket.Double-click on "PHP Manager". Next, click on "Enable or disable an extension" and enable the extensions php_imap.dll,
php_intl.dll, and php_opcache.dll.
</p>
<br />

<h2>Rename: ost-config in PHP folder</h2>
<p>
<img src="https://i.imgur.com/OoNt5Dw.png"/>
</p>
<p>
In file explorer go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename it ost-config.php.
</p>
<br />

<h2>Assign Permissions in ost-config.php and continue to setup osTicket</h2>
<p>
<img src="https://i.imgur.com/upyBLPk.png"/>
</p>
<p>
<img src="https://i.imgur.com/FQjsr9o.png"/>
</p>
<p>
Right click on ost-config.php and select properties, security, and advanced. In the advanced security settings, select disable inheritance and remove all inherited permissions. Next, add a new permission for everyone and select "full control". Make sure to apply the changes you make.
</p>
<br />

<h2>Continue Setting up osTicket in the browser</h2>
<p>
<img src="https://i.imgur.com/QNs5mIX.png"/>
</p>
<p>
Give your helpdesk a name, enter a default email, and complete the Admin User section. Do NOT click "Install" yet. We need to install HeidiSQL on our virtual machine first.
</p>
<br />

<h2>Install HeidiSQL to link MySQL database to osTicket</h2>
<p>
<img src="https://i.imgur.com/wO16jAi.png"/>
</p>
<p>
<img src="https://i.imgur.com/8LimlRM.png"/>
</p>
<p>
Download and install HeidiSQL. Create a new connection to the database and enter the password from MySQL setup to connect the database. Next, create a database called "osTicket". Finish setting up osTicket in the web browser and click "Install Now".
</p>
<br />

<h2>Clean Up</h2>
<p>
<img src="https://i.imgur.com/gCoJpRf.png"/>
</p>
<p>
Go to C:\inetpub\wwwroot\osTicket and delete the "setup" folder. Set permissions to “Read” only in C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<br />
