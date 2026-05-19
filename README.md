
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory User & Client Management Lab (Azure)</h1>
This project builds on an existing Active Directory environment deployed in Microsoft Azure and focuses on core domain administration tasks, including user and group management, Organizational Unit (OU) structure, client domain joining, Remote Desktop access configuration, and automated user provisioning using PowerShell. The project demonstrates practical identity and access management workflows within a cloud-hosted Windows domain using industry-standard tools and configurations..<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)




<h2>Deployment and Configuration Steps</h2>
<img width="400" height="241" alt="Active Directory Configuration" src="https://github.com/user-attachments/assets/ac2c683e-6aae-4624-9333-5326e7cb3095" />
<p>With the domain environment already established, the project continues by expanding domain management and user access. After initially accessing the client and domain controller with local credentials, Organizational Units are created for Employees and Administrators, followed by the creation of a dedicated Domain Admin account. The client virtual machine is then joined to the domain and organized within a Clients OU. Remote Desktop access is configured to allow standard domain users to sign in, and PowerShell automation is used to bulk-create user accounts within the Employees OU to simulate real-world provisioning tasks.




Key Actions
- Step  Create Organizational Units for Employees and Admins
- Step Create Organizational Units for Employees and Admins
- Step Join client VM to the domain
- Step Configure Remote Desktop access for domain users
- Automate bulk user creation with PowerShell









