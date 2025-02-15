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
- prepare the AD infrastructure in Azure
- Deploying active directory
- create users with powershell
- Group policy and managing accounts

<h2>Deployment and Configuration Steps</h2>

<h3>1. Prepare the AD infracstructure in azure</h3>

- create a resource group
 - go to the azure portal and create a new resource group
   
![image](https://github.com/user-attachments/assets/47af0d43-527b-4b2d-bfaf-49a2700c8dc4)

<h3>2. Create  a virutal network and subnet</h3>

- Create a virtual Network:
   - Create a virtual network with a subnet to host the VMs
  
![image](https://github.com/user-attachments/assets/1dc27e93-4cbf-403d-b048-12304d996ba5)

<h3>3. Create the domain controller VM</h3>

- name the VM DC-1
- ensure the vm is on the vnet created prior

![image](https://github.com/user-attachments/assets/ad54fdfa-d3fb-410d-8b14-02dcf4575274)

4. <h3>Set Static Private IP for DC-1:</h3>
   - After the VM is created, navigate to its Network Interface Card (NIC) settings and set the private IP to static.
     
     ![image](https://github.com/user-attachments/assets/7ee0a079-28a2-4d60-9004-347e5cb35945)

5. <h3>Disable windows firewall:</h3>

- Log in to DC-1, disable the Windows Firewall for testing connectivity.

![image](https://github.com/user-attachments/assets/9a5b2f49-1590-475e-9a15-733959984588)

<h2>Setup client-1 in Azure</h2>

<h3>1. Prepare the AD infracstructure in azure</h3>

- create the client vm
  - name the vm client-1
  
 ![image](https://github.com/user-attachments/assets/700e74a1-d524-4b34-b136-670b55940d16)

 <h3>2. Attach Client-1 to the same region and Vnet</h3>
 
 - ensure it is in the same virtual Network and Subnet like dc-1



