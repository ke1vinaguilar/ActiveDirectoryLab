<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
In this lab I'm going to walk through how to create an Active Directory home lab Environment using Oracle Virtual Box. Configuring and running this lab will help develop understanding of how active directory and windows networking works.


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10 </b> (21H2)
- <b>Servers 2019</b>

<h2>Diagram</h2>
<p align="center">
<img src="https://i.imgur.com/Jtqs9WI.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
 </p>

<h2>Program walk-through:</h2>

<p align="center">
Download Oracle Virtual Box: <br/>
<a href="https://www.virtualbox.org/">Oracle Virtual Box</a>
<br />
<br />
Download Windows 10 ISO File: <br/>
<a href="https://www.microsoft.com/en-us/software-download/windows10">Windows 10 ISO</a>
<br />
<br />
Download Windows Server 2019 ISO File: <br/>
<a href="https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019">Windows Server 2019 ISO</a>
<br />
<br />
Create a new virtual machine by clicking on "New" in VirtualBox, and name it "DC": <br/>
<img src="https://i.imgur.com/5bVPho9.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Configure the virtual machine hardware:  <br/>
<img src="https://i.imgur.com/eRMOfMG.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Go to “Advanced Settings” and change “Shared Clipboard” and Drag’nDrop” from “Disabled” to “Bidirectional”: <br/>
<img src="https://i.imgur.com/3VDYXnu.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Go to Network Tab and create 2 NICs (Network Interface Controller) 1(for the Internet running NAT) 2(one for the internal VMWARE network):  <br/>
<img src="https://i.imgur.com/fU3Cusr.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
 <img src="https://i.imgur.com/fU3Cusr.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Install the Windows 2019 Server ISO file:  <br/>
<img src="https://i.imgur.com/CiuoT8n.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Windows Server 2019 Standard Evaluation (Desktop Experience):  <br/>
<img src="https://i.imgur.com/uqClmrU.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Create Password:  <br/>
<img src="https://i.imgur.com/xZNEDn1.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Login to Sever as Administrator and Click on “Devices” and then click on “Insert Guest Additions CD image…”:  <br/>
<img src="https://i.imgur.com/aLna3mm.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Open up “File Explorer” then go to “My PC”. Click on “CD Drive (D:) VirtualBox Guest Additions:  <br/>
<img src="https://i.imgur.com/wExAX4Z.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Run “VBoxWindowsAdditions-amd64” and install (make it less laggy and box resizes when you expand:  <br/>
<img src="https://i.imgur.com/d3y4wGS.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Shut down VM and Restart VM. Log back in. Identity NICS:  <br/>
<img src="https://i.imgur.com/kQHKlbJ.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Rename the PC from “WIN-HQ32MRAVPFO” to “DC” and Restart VM:  <br/>
<img src="https://i.imgur.com/20yDJQe.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Assign an IP address to the Internal NIC (1.Properties,2. Internet Protocol Version 4(TCP/IPv4):  <br/>
<img src="https://i.imgur.com/8vYxYjG.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Domain Controller itself serves as the Default Gateway, when we install Active Directory it automatically installs DNS, the server is going to use itself as the DNS server (enter own IP address or loopback address:  <br/>
<img src="https://i.imgur.com/oN3CTOg.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
 Install Active Directory Domain Services (ADDS) and Create a Domain:  <br/>
<img src="https://i.imgur.com/IZ3bLj6.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Active Directory Domain Services” and Install:  <br/>
<img src="https://i.imgur.com/1QAwW3Z.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Create the Domain:  <br/>
<img src="https://i.imgur.com/IKJO4Yu.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click “Add new forest” and fill in the Root domain name: “mydomain.com”:  <br/>
<img src="https://i.imgur.com/uIhFfMP.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Type password as “Password1” and Click “Next” until you get the option to “Install”:  <br/>
<img src="https://i.imgur.com/8LJYmxo.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Log into “MYDOMAIN/Administrator” profile
-Create own dedicated domain admin profile
-Click “Start”
-Click “Windows Administrative Tools”
-Click “Active Directory Users and Computers”
-Right-click “mydomain.com” and select “New”
-Select “Organizational Unit” and name it “_ADMINS”
-Uncheck “Protect container from accidental deletion”:  <br/>
<img src="https://i.imgur.com/ryWjo8T.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Create a new user inside of “Admins”
-Right-click “Admins” and select “New”
-Select “User” and Fill In:  <br/>
<img src="https://i.imgur.com/X2rcOyd.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Set password to “Password1” and uncheck “User must change password at next logon” and check “Password never expires”:  <br/>
<img src="https://i.imgur.com/L1ATXqu.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
 Set user as an Admin
-Click the profile to go to properties
-Click on “Member of” and add “Domain Admins” group:  <br/>
<img src="https://i.imgur.com/fvC9XHw.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Sign out of Domain Controller and sign back in as the new Admin profile we just created:  <br/>
<img src="https://i.imgur.com/66vx3qv.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Install RAS/NAT (when we create our Windows 10 client it allows the client to be on the private virtual network with the ability to still access the internet through the domain controller)
-Install RAS/NAT on the Domain Controller. Click on “Add Roles and Features” in Server Manager:  <br/>
<img src="https://i.imgur.com/NWrR5LE.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Remote Access”:  <br/>
<img src="https://i.imgur.com/xVN1AG0.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Routing” and Install:  <br/>
<img src="https://i.imgur.com/wrgfuOw.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<img src="https://i.imgur.com/rDqTjuA.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Tools” and select “Routing and Remote Access”:  <br/>
<img src="https://i.imgur.com/OVDLcok.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Right-click on “DC” and select “Configure and Enable Routing and Remote Access”:  <br/>
<img src="https://i.imgur.com/NsdhW20.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Network address translation (NAT)”:  <br/>
<img src="https://i.imgur.com/SYuVhJ1.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “INTERNET” when selecting “Use this public interface to connect to the Internet”:  <br/>
<img src="https://i.imgur.com/Rz5cn12.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Finish” to complete the setup wizard:  <br/>
<img src="https://i.imgur.com/7zYa4r4.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Setup DHCP Server on the Domain Controller which allows our Windows 10 client to get an IP address so they can browse the internet
-Go back to Server Manager and select “Add roles and features”
40. Select “DHCP Server” and “Add Features”:  <br/>
<img src="https://i.imgur.com/qSvElmZ.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Go to “Tools” and Select “DHCP”:  <br/>
<img src="https://i.imgur.com/Y0XjfF0.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Expand “dc.mydomain.com”:  <br/>
<img src="https://i.imgur.com/sgdawPm.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Expand “IPv4”, Right-click and select “New Scope”:  <br/>
<img src="https://i.imgur.com/jWqAgZ7.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Name the “New Scope” after the Range “172.16.0.100-200”:  <br/>
<img src="https://i.imgur.com/sV3VzZf.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Fill in the IP Range as the following:
Start IP address: 172.16.0.100
End IP address: 172.16.0.200
Length: 24
Subnet Mask: 255.255.255.0:  <br/>
<img src="https://i.imgur.com/NItj5O6.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Yes, I want to configure these options now”:  <br/>
<img src="https://i.imgur.com/PUCxS10.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Clients are going to use the Internal NIC of the Domain Controller as their default gateway/ router
-Enter 172.16.0.1 and select “Add”:  <br/>
<img src="https://i.imgur.com/PBpkiBc.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Yes, I want to activate this scope now?” and “Finish”:  <br/>
<img src="https://i.imgur.com/xJquN1T.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Right-click the “domaincontroller.mydomain.com” and select “Authorize”:  <br/>
<img src="https://i.imgur.com/RJ5AptT.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Configure this local server” in Server Manager (usually don’t want to do this in a production environment but this is a lab):  <br/>
<img src="https://i.imgur.com/HS0OgHm.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Disable the “IE Enhanced Security Configuration”:  <br/>
<img src="https://i.imgur.com/qtrxUG0.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Open browser and type in https://github.com/joshmadakor1/AD_PS/:  <br/>
<img src="https://i.imgur.com/I8aBQfc.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Save “AD_PS-master.zip” in Desktop. Extract the zip folder on the Desktop:  <br/>
<img src="https://i.imgur.com/bAWKAgg.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Open the AD_PS-master folder
- Open the “names” Plain Text File
-Add “Kelvin Aguilar” we’re going to use this file to programmatically create all of these users:  <br/>
<img src="https://i.imgur.com/kPjEEqj.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Start” and go to “Windows PowerShell”, Right-click on “Windows PowerShell ISE (x86)”
-Click on “More” and click on “run as administrator”:  <br/>
<img src="https://i.imgur.com/yGsFvbk.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Open Script”
-Click on “My Desktop”
-Open the “AD_PS-master” folder
-Click on the “1_CREATE_USERS” PowerShell Script:  <br/>
<img src="https://i.imgur.com/VyoAqS6.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Enable the execution of all scripts by typing “Set-ExecutionPolicy Unrestricted” in the command line
-Select “Yes to all”:  <br/>
<img src="https://i.imgur.com/NJg733F.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Change directory to be able to run the script by typing 
“cd c:\users\a-kaguilar\desktop\AD_PS-master” in the command line:  <br/>
<img src="https://i.imgur.com/1gQkIs4.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Type “ls” in the command line to see the files:  <br/>
<img src="https://i.imgur.com/xVcY3Me.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Press “Run Script” or F5:  <br/>
<img src="https://i.imgur.com/Xi96NHm.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Create Windows to Virtual Machine in Virtual Box
-Click on “New” in Virtual Box:  <br/>
<img src="https://i.imgur.com/HTp7Tcq.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
-Configurations
 <img src="https://i.imgur.com/IbJm0X2.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Right Click on “CLIENT1 and select “Settings”
-Click on “Advanced” and change both “Shared Clipboard” and “Drag’n’Drop” to “bidirectional”:  <br/>
<img src="https://i.imgur.com/lXgpvFw.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Network” and change “Attached to” to “Internal Network”:  <br/>
<img src="https://i.imgur.com/9lUFqvT.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Start “CLIENT1” and select the Windows 10 iso file. Select “I don’t have a product key”
67.Select “I don’t have a product key”:  <br/>
<img src="https://i.imgur.com/ySGpvPH.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Select “Windows 10 Pro”:  <br/>
<img src="https://i.imgur.com/Up0o5FF.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Name the PC “user” and don’t set up a password:  <br/>
<img src="https://i.imgur.com/5zqpyqI.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Type “ipconfig” in the command prompt line to check out the information of the network:  <br/>
<img src="https://i.imgur.com/rYIlDob.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Right Click the Windows Start button and select “System
-Select “rename this PC (advanced)”:  <br/>
<img src="https://i.imgur.com/ooTeZks.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Click on “Change” and rename the Computer name to “CLIENT1”
-Select “Domain” in “Member of” and type in “mydomain.com” to join the domain:  <br/>
<img src="https://i.imgur.com/h1psb6z.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Type in “kaguilar” as username and “Password1” for the password as credentials to make changes:  <br/>
<img src="https://i.imgur.com/ok7JyHu.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
