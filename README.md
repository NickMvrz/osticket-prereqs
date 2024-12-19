<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

- <p> All the files needed to install osTicket can be located here.</p> 
- ### [Download Now](https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 📁


<h2>What is osTicket?</h2>
- osTicket is an open source ticketing system that organizations use to manage customer support queries regarding computer issues. 
<p>
   
</p>

- In this tutorial I will outline the prerequisites and installation process of the open-source help desk ticketing system osTicket. After osTicket is installed, I will explore and test the features of the osTicket ticketing system to get an idea of what it's like to handle tickets and interact with users.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create Virtual Machine (In Microsoft Azure)
- Install the files located above: osTicket v1.15.8, HeidiSQL, MySQL, PHP, C++ Redistributable

<h2>Installation Steps</h2>

<p>
<h3 align="center">1.) On Azure, we will create a resource group (used to contain and manage our resources, in this case, a virtual machine.)</h3>
<br />

   
![68747470733a2f2f692e696d6775722e636f6d2f644546316337682e706e67](https://github.com/user-attachments/assets/724a3ded-6e61-4126-9574-383866c03035)


<h3 align="center">2.) Open the Windows app (Mac) or Remote Desktop Connection (Windows) and connect to the Virtual machine with the public IP address created within the VM.
<br /> 
<p>
 
</p>
<img width="470" alt="Screenshot 2024-12-17 at 5 17 53 PM" src="https://github.com/user-attachments/assets/b24a590c-267b-4a61-ade7-d099515f1ea0" />

<h3 align="center"> OR </h3>

![255309386-2e71fd86-4198-47aa-aa1a-d0aed1b8e0eb](https://github.com/user-attachments/assets/a0d2d011-0ca9-4549-b215-700447cc2373)

 
<h3 align="center">3.) Now that we have logged on we need to enable IIS. (Internet Information Services) This web server will run on the VM and allow me to "serve" osTicket.</h3>
<p>
 
</p>

![68747470733a2f2f692e696d6775722e636f6d2f694230444452642e706e67](https://github.com/user-attachments/assets/75fa8dd3-7da2-4be7-b668-6b948fca2be1)

</p>
<br />
<h3 align="center">4.) Select IIS, worldwide web services, application development features, and click on CGI.
<p>
 
</p>


 <img width="413" alt="Screenshot 2024-12-17 at 1 07 50 PM" src="https://github.com/user-attachments/assets/d4ce3c7c-441e-4993-a6a3-325d4dae0d11" />

<h3 align="center">5.) After this is completed, I will install PHP manager for Internet Information Services. This is a computer language that osTicket runs on, and will be needed to install it. </h3>


<img width="506" alt="Screenshot 2024-12-17 at 5 28 07 PM" src="https://github.com/user-attachments/assets/38916a67-5b9f-42b7-a464-bed27e763058" />



<h3 align="center">6.) Then we will install the Rewrite module. This is used to manage and rewrite URLS on a web server. Just know that osTicket requires specific URL formats, and this will allow compatibility with osTicket.</h3>

![255307784-28cf2dd0-d39e-45f8-a01b-61aec6657228](https://github.com/user-attachments/assets/c04656b0-1590-4d60-80d6-fe163f4b5dd3)


<h3 align="center">7.) In the windows :C drive, create a folder called "PHP". Then we will unzip the php-7.3.8-nts-Win32-VC15-x86 downloaded earlier and place it into the PHP folder.</h3>

<img width="1126" alt="Screenshot 2024-12-17 at 1 19 40 PM" src="https://github.com/user-attachments/assets/b3861c60-3cec-4456-b1ed-b06b8a0d877c" />


<h3 align="center">8.) Install VC_redist.x86
<p>
 
</p>
<img width="486" alt="Screenshot 2024-12-17 at 5 31 04 PM" src="https://github.com/user-attachments/assets/8f7f732c-b9a0-4419-95d2-77af67dae1a5" />


<h3 align="center">9.) Install mysql-5.5.62-win32. This will be used to store the data from osTicket (user accounts, ticketing, etc.), choose typical setup, choose standard configuration. Create a username and password. (anything will work)</h3>

<img width="497" alt="Screenshot 2024-12-17 at 5 31 38 PM" src="https://github.com/user-attachments/assets/854a52e1-cbc0-4d9c-8c75-ec2505312776" />

![68747470733a2f2f692e696d6775722e636f6d2f7a646857584e782e706e67](https://github.com/user-attachments/assets/344af9b4-b526-4159-8bea-9a7985cbfefd)

<h3 align="center">10.) Open IIS as an admin, and from here we will register PHP so our web server can acknowledge the existence of PHP on our VM. Click PHP Manager > register new PHP version > and browse to the previous "PHP" file that was created, click the "php-cgi" option. Restart IIS from the Home Screen to reload the web server.</h3>

<img width="1512" alt="Screenshot 2024-12-17 at 1 41 28 PM" src="https://github.com/user-attachments/assets/ad5e526c-5dc2-4a4c-831e-1c2b5b1b6334" />


<h3 align="center">11.) Minimize IIS, and extract the osTicket-v1.15.8 folder downloaded earlier.</h3>


<img width="389" alt="Screenshot 2024-12-17 at 5 37 48 PM" src="https://github.com/user-attachments/assets/3c5145bb-8581-40dd-a081-ff87f120bfb3" />

<h3 align="center">12.) Copy the "upload" folder located in the file, and go to c:\inetpub\wwwroot and paste it here. Rename the upload folder to "osTicket".</h3>

<img width="966" alt="Screenshot 2024-12-17 at 5 39 38 PM" src="https://github.com/user-attachments/assets/21f14d65-414c-48d4-a4fc-d0cb0631874d" />


<h3 align="center">13.) Restart IIS, and go to the connections list. Select os-ticket-vm>sites>default website, and click the osTicket folder. In the manage folder section, click "Browse *:80 (http)"</h3>

<img width="1121" alt="Screenshot 2024-12-17 at 5 40 26 PM" src="https://github.com/user-attachments/assets/c0628e88-f411-4c0f-b551-f9fae4411a30" />


<h3 align="center">14.) Some extensions aren't enabled. In order to fix this, we will go back to IIS, back to the osTicket folder, select PHP Manager, and select "enable or disable an extension". Enable: php_imap.dll, php_intl.dll, php_opcache.dll.</h3>

<img width="1096" alt="Screenshot 2024-12-17 at 2 08 22 PM" src="https://github.com/user-attachments/assets/813224ac-7a1a-4e35-b75d-f24b9bebc8d8" />


<h3 align="center">15.) If you refresh the osTicket installer page, you should see all extensions are enabled except for 2 at the bottom.</h3>

<img width="1511" alt="Screenshot 2024-12-17 at 2 11 30 PM" src="https://github.com/user-attachments/assets/3ea7dbe7-a2c5-4609-b444-1258f6a5d50d" />



<h3 align="center">16.) Next we will rename out-config.php (for testing purposes) We will go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the "ost-sampleconfig.php" to "ost-config.php". </h3>

<img width="1127" alt="Screenshot 2024-12-17 at 2 12 22 PM" src="https://github.com/user-attachments/assets/0d4b035d-7bed-40b3-8b02-8e05cc1e850d" />


<h3 align="center">17.) Right click and select Properties>security>advanced>disable inheritance>Remove all>add>Everyone </h3>

<img width="920" alt="Screenshot 2024-12-17 at 2 17 42 PM" src="https://github.com/user-attachments/assets/e7aecc45-e134-4098-ab98-673b57264028" />


<h3 align="center">18.) Go back to the osTicket browser and select continue, enter basic information. Before I click install now, I need to install HeidiSQL to full setup our database for osTicket.</h3>

![68747470733a2f2f692e696d6775722e636f6d2f59737a6849706c2e706e67](https://github.com/user-attachments/assets/6964d49d-fe55-443d-b29b-ad47a1fd3b38)




<h3 align="center">19.) Select new +, enter the user and password we created for the MySQL, and open.</h3>


![68747470733a2f2f692e696d6775722e636f6d2f397435314170522e706e67](https://github.com/user-attachments/assets/4076ec15-bcfa-41da-b7c5-082b28701959)

<h3 align="center">20.) Click Unnamed>create new>database>name:osTicket</h3>

![68747470733a2f2f692e696d6775722e636f6d2f76587a6d5171672e706e67](https://github.com/user-attachments/assets/fd8d0400-7da8-4617-a068-d924b4919c55)

<h3 align="center">21.) Head back to the osTicket browser, type the MySQL database name we just created (osTicket), our user and password, select install now.</h3>

<h2>osTicket is now installed.</h2>

<img width="829" alt="Screenshot 2024-12-17 at 2 26 02 PM" src="https://github.com/user-attachments/assets/026e88ee-34a9-4bdd-8c8e-efb1658f1f6f" />


</p>

