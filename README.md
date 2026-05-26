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
- This is a map of all IP addresses that attempted to connection to my honeypot. As you can see there are quite a lot, 286K connections from Spain alone. All of these attemped logins simply having the honeypot connected to the internet. The only alure to my honeypot was the name "ADMIN-VNET-EAST-1". This was enough to have people attempt to login with usernames such as "Admin", "Administrator", "ADMINISTRATOR", "User", "1", Guest", and "VNET".

<h2>How I Made This</h2>

- I was able to assemble this home lab within the free trail of Microsoft Azure. To start, I created a Resource Manager entitled "SOCLAB". Here is a Resource Diagram of all the components within the Resouce Group.
<div align="center">
  <img src="SOCLAB.png" alt="SOCLAB" width="900">
</div>
<br />
Let's break this down...


<h2>Fig. 2: Resource Group Creation:</h2>
<div align="center">
  <img src="SOCLABRG.png" alt="SOCLAB" width="900">
</div>
<br />

- Start by creating a Resource Group in Azure. I named mine "SOCLAB" and set the location as East US 2, but the exact location does not matter too much.

<h2>Fig. 3: Virtual Machine Creation:</h2>
<div align="center">
  <img src="VMLayout.png" alt="SOCLAB" width="900">
</div>
<br />

- <b>Create a virtual machine</b> within the Resouce Group. I named mine "ADMIN-VNET-EAST-1". This name should be something enticing for hackers or bots to try and break into. Any name that sounds important that isn't "Honeypot" should be work just fine. Also make sure to create a memorable password so you don't have to reset it 3 times like I did.
- <b>Configure the network</b> to make the VM vulnerable. Go into the Network Settings of the VM, and hit <b>Create port rule</b>. Add a port rule which allows all inbound traffic from all ports. I threw the word "DANGER" into the name of my rule to signify that allowing all traffic is indeed dangerous

<h2>Fig. 4: Virtual Machine Creation:</h2>
<div align="center">
  <img src="VMLayout.png" alt="SOCLAB" width="900">
</div>
<br />
