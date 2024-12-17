<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

What is osTicket?
- osTicket is an open source ticketing system that organizations use to manage customer support queries regarding computer issues.

What's the goal?
 This goal is to show a tutorial that outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. After osTicket is installed, I will explore and test the features of the osTicket ticketing system to get an idea of what it's like to handle tickets and interact with users.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>
- Create a Virtual Machine within Microsoft Azure
- Enable Internet Information Services within VM
- Enable CGI (within Internet Information Services)

<h2>Installation Steps</h2>

<p>
  
<img src="https://imgur.com/a/5ULdZMG" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
On Azure, we will create a resource group (use to contain and manage our resources, in this case, a virtual machine.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 
  -Once the virtual machine is deployed, I will login with the credentials I created. Then when we are in the VM we will enable IIS. (Internet Information Services) This web server will run on the VM and allow me to "serve" osTicket.
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-Access the control panel and click the turn on windows features option.
</p>
<br />
