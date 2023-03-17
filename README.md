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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla ariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
