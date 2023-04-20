<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
In this lab we're going to walk through how to create am Active Directory home lab Environment using Oracle Virtual Box. Configuring and running this lab will definitely help develop your understanding of how active directory and windows networking works, so I'd highly recommnend running through it a couple times, ask questions where stuff is unclear, and eventually try to build it on your own without watching. Please let me know if you have any questions!
<br />


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
Create a new virtual machine by clicking on "New" in VirtualBox, naming it "DC", and selecting the "Windows Server 2019" ISO file as the boot media: <br/>
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
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Active Directory Lab Steps"/>
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
