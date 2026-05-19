<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This project demonstrates the deployment of a traditional on-premises Active Directory Domain Services (AD DS) environment using Microsoft Azure virtual machines. A Windows Server VM was configured and promoted to a domain controller with integrated DNS, and a Windows client VM was provisioned and joined to the new domain within the same virtual network. The lab successfully validates domain join, DNS resolution, and authentication using RDP and PowerShell, replicating a real-world enterprise Active Directory infrastructure scenario hosted in the cloud..<br />





<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

<img width="400" height="350" alt="image" src="https://github.com/user-attachments/assets/729569d4-d711-44f3-bc04-0c0620400853" />

- Step 1. Create VM Client 1
- Step 2. Create VM Server Domain Controller
- Step 3. Install Active Directory









<h1>Deployment and Configuration</h1>





1. <h1>CREATE RESOURCE GROUP<h1>
Log into Azure Portal, and in the search bar type "Resource Groups", select Resource Groups and press "+ Create" to create a resouce group. Name your resource group "rg-ad-lab" and select "Review + Create", finally "Create".

<img width="400" height="288" alt="image" src="https://github.com/user-attachments/assets/06f1ce8c-adb5-4123-8d58-4b154e1afe9a" />
<img width="400" height="288" alt="image" src="https://github.com/user-attachments/assets/80d62807-33c5-45fa-9f3a-adfeb2665daf" />






2.  <h1>CREATE VIRTUAL NETWORK <h1>
In the search bar, type "Virtual Networks", select Virtual Networks and press "+ Create" to start creation of your Virtual Network. Select the resource group we just made and name your virtual network "vnet-ad-lab", select "Review + Create" and finally "Create".

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/6cb2e69a-9e74-46ef-aedd-9940b27d19a3" />





 3.  <h1>CREATE VM DOMAIN CONTROLLER <h1>

   In the search bar, type "VM", select Virtual Machines and press "+ Create" and select "Virtual Machines" to start creation of your Virtual Machine. Select the "rg-ad-lab" as the resource group, name your vm "vm-dc-1". For Image, select "Windows Server 2022, Datacenter: Azure Edition - x64 Gen2" For Size, select any with 2 VCPUs and at least 16 GB Ram. Set your username and password in the Admin Account section. Near the bottom, select "Next : Disk >" continue on to "Next : Networking







