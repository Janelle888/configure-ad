<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Set up Resources
- Install Active Directory
- Set up Domain Controller
- Join Windows 10 Virtual Machine to Domain Controller 

<h2>Deployment and Configuration Steps</h2>

<p>
</p>
<p>

- Set up your Domain Controller Virtual Machine, then set up Windows 10 Virtual Machine. Make sure that both resources are in the same virtual network and resource group.
  
</p>
<br />

<p>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/59a9e88a-b420-4199-9f4e-26434f267597)

</p>

- We then have to go to our Domain Controller change the Nic Private IP address from Dynamic to Static
<p>
<br/>
  
- Log into the Domain Controller so that we can open a hole in its fire wall, enable ICMPv4 which will allow us to ping this VM from the other one. Also enable IMCP Echo Request.

</p>
<br />

<p>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/45a8a466-36f1-4f44-8161-4a38ab604e6e)

![image](https://github.com/Janelle888/configure-ad/assets/142438143/ae61dfb3-0002-4724-bbaa-4dfca71cabb9)


</p>
<p>
<br/>
  
- Next we are going to our Windows 10 VM to set up Active Directiory, go to Add Roles and Features and install Acitve Directory.
  
</p>
<br />

![image](https://github.com/Janelle888/configure-ad/assets/142438143/37aee064-d06b-475a-96be-21d0e3e8d4ef)

<p>
<br/>

- Turn your server into a Domain Server and create the Domain name.
<p>
<br/>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/f292524d-f6e7-4b65-a290-f6a7e13a1d5a)

  
</p>
<br />

- In Active Directory Users and Computers create 2 new organizational units called  “_EMPLOYEES” and “_ADMINS”.

<p>
<br/>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/f312ceb0-7e6a-41a4-b04b-2cfe9cbad7ec)


</p>
<br/>

- Set Domain Controller as your DNS Server so that you can control the domain controller from the Windows 10 VM. Go to the azure portal and find the domain controller's private IP address.
  
<p>
<br/>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/0321dbac-a54b-4261-912c-ec0ba3693714)


<p>
<br/>
  
  - Go to the windows 10 VM in azure and select networking > DNS servers. Select custom, put in the domain controllers private address and save. 
  
</p>
<br/>

![image](https://github.com/Janelle888/configure-ad/assets/142438143/1abdf40b-bc9c-47aa-9be1-6dd61ef6890e)


</p>
<br />

- Line
  
<p>
<br/>
  
Image

<p>
<br/>
  
- Line
  
</p>
<br />

Image

<p>
<br/>
  
  - Line
  
</p>
<br/>

Image

</p>
<br />

- Line
  
<p>
<br/>
  
Image

<p>
<br/>
  
- Line
  
</p>
<br />

Image
