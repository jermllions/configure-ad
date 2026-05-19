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


<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/ff198924-7c9d-4cb3-9bde-3895bbecc1d2" />






4. <h1>CREATE VM CLIENT<h1>
In the search bar, type "VM", select Virtual Machines and press "+ Create" and select "Virtual Machines" to start creation of your Virtual Machine. Select the "rg-ad-lab" as the resource group, name your vm "vm-client-1". For Image, select "Windows 10 Enterprise, version 22H2 - x64 Gen 2" For Size, select any with 2 VCPUs and at least 16 GB Ram. Set your username and password in the Admin Account section. Near the bottom, mark the checkbox in the Licensing section and select "Next : Disk >" continue on to "Next : Networking >".






<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/3ab922fc-cfc1-48e8-83dc-ec02a235dbb3" />






Next Restart "vm-client-1" within the Azure Portal by going to your vm list. Mark the checkbox for "vm-client-1" and select "Restart" near the top.While on this screen, copy/note "vm-client'1" Public IP Address, we'll need it to Login.



<img width="1534" height="594" alt="image" src="https://github.com/user-attachments/assets/1c60a06a-ebaf-4365-afbf-9a7910df135a" />



Next On your local computer (Windows or macOS), open another instance of Remote Desktop client and connect to the VM Client 1 using public IP address, you'll be prompted to enter your credentials you created when creating this VM. Next prompt, select yes, and your VM Client 1 will now boot. Open PowerShell and attempt to ping your Domain Controller's Private IP Address. Ensure the ping the succeded, run ipconfig /all. The output for DNS Settings should now show "vm-dc-1"'s Private IP Address.



<img width="643" height="727" alt="image" src="https://github.com/user-attachments/assets/b0b9b95d-efec-47f8-88e8-416e5ef8561c" />





<h1>5. <h1>INSTALL ACTIVE DIRECTORY<h1>



Return to our Domain Controller from Step 3. View or Open "Server Manager > Dashboard". Select option 2. Add roles and features. Select "Next" 3 times, until we arrive at "Server Roles". Here select "Active Directory Domain Services". Select "Next" 3 times again. On the Confirmation screen, mark the checkbox "Restart the destination server automatically..." , and select "Install".


<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/2770e109-d80d-4330-830a-a396273f40d9" />



Once feature is finsihed installing, select "Close". On your Server Manager Dashboard, select the notifications icon.

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/85f7871f-368a-4e18-aa12-10c8655275e0" />



 From here, select "Promote this server to a domain controller". In the Domain Configuration screen, select "Add a new forest" and in Root domain name field, type "mydomain.com". (you may name the forest anything) Select "Next", in the Domain Controller Options, you will need to set the DSRM Password here. Select "Next", be sure to unmark the DNS Delegation checkbox here, select 4 more times from here, and lastly "Install". The VM will install the new forest and will sign out automatically.


 <img width="762" height="552" alt="image" src="https://github.com/user-attachments/assets/2c2bb434-5a4d-4a5e-af97-d216318c08db" />





 Once signed out, RDP will restart for the VM, select "More Options" and clear the username field, and enter mydomain.com\<yourcreatedcredentials> and password.


 <img width="399" height="495" alt="image" src="https://github.com/user-attachments/assets/c60f86d0-4e42-4052-bdfc-f21f10277a6e" />





 Once logged back into the Domain Controller, we can review the Server Manager Dashboard and verify that the Active Directory Domain Services and DNS roles are installed and running!




 <img width="1527" height="736" alt="image" src="https://github.com/user-attachments/assets/1b508cc4-8957-4479-bf49-a9b4f7f1b7db" />





   







