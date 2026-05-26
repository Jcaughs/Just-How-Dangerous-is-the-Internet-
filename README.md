<h1>How Dangerous is the Internet?...It's Pretty Bad.</h1>

<h2>Description</h2>
This home lab project is meant to signify how bad it is to host an IoT device with default credentials on the open internet. Below is the documentation and steps I took to create a simple honeypot on Microsoft Azure. The main idea is to host a vulnerable virtual machine on a vulnerable network and see who tries to connect to it via virtual desktop and from where. I used workbook on Microsoft Defender to map all IP's who failed to login (Event ID 4625).
<br />


<h2>Languages and Utilities Used</h2>

- <b>KQL
- Windows Security Logs</b> 

<h2>Environments Used </h2>

- <b>Microsoft Azure
- Windows 11 VM
- Azure Network Interface
- Azure Log Analytics Workspace
- Azure Virtual Network
- Microsoft Defender Workbook (Sentinel)</b> 

<h2>Fig. 1: Honeypot Connections Within 144 Hours:</h2>
<div align="center">
  <img src="4625EventIDMap.png" alt="EventIDMap" width="900">
</div>
This is a map of all IP addresses that attempted to connection to my honeypot. As you can see there are quite a lot, 286K connections from Spain alone. All of these attemped logins simply having the honeypot connected to the internet. The only alure to my honeypot was the name "ADMIN-VNET-EAST-1". This was enough to have people attempt to login with usernames such as "Admin", "Administrator", "ADMINISTRATOR", "User", "1", Guest", and "VNET".

<h2>How I Made This</h2>

I was able to assemble this home lab within the free trail of Microsoft Azure. To start, I created a Resource Manager entitled "SOCLAB". Here is a Resource Diagram of all the components within the Resouce Group.
<div align="center">
  <img src="SOCLAB.png" alt="SOCLAB" width="900">
</div>
<br />
Let's break this down...

