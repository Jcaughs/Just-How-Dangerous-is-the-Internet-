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

<h2>Honeypot Connections Within 144 Hours:</h2>
<div align="center">
  <img src="4625EventIDMap.png" alt="PythonScript" width="900">
</div>
