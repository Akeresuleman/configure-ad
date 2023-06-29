<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure
- Ensure Connectivity between the client and Domain Controller
- Install Active Directory
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain (mydomain.com)
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>

<img width="910" alt="image" src="https://github.com/Akeresuleman/configure-ad/assets/137787129/dac86b99-10d1-470d-862c-a9ffe22bf20b">

<img width="691" alt="image" src="https://github.com/Akeresuleman/configure-ad/assets/137787129/e56568cb-8af4-4173-b384-f1bc55dd4bf3">

![image](https://github.com/Akeresuleman/configure-ad/assets/137787129/690ac50d-596c-4f3f-aee6-0e2121b8a3db)

![image](https://github.com/Akeresuleman/configure-ad/assets/137787129/125dcce2-c2cd-4c1a-84b5-d348c02ff8e3)
![image](https://github.com/Akeresuleman/configure-ad/assets/137787129/9ce0eb6d-650c-4f6c-b21c-25e6e181f901)

  
![image](https://github.com/Akeresuleman/configure-ad/assets/137787129/84faaa7c-330b-4945-b192-380a108b8936)
<img width="577" alt="image" src="https://github.com/Akeresuleman/configure-ad/assets/137787129/9943a3ad-866e-41f1-9daf-a2550bd4fc9c">
![image](https://github.com/Akeresuleman/configure-ad/assets/137787129/92bdc3a1-7235-4124-94d3-5134ca0fb135)



</p>
<p>
Created my domain controllere VM named vmdc with vnet, vmdc-vnet and setup it's NIC private IP to static. created another virtual machine named client running windows 10 with the same vnet as vmdc. I then login client using a RD and ping vmdc's private ip which wasn't responding. I further login vmdc using another RD and enabled ICMPv4s in its windows firewall and ping vmdcs private ip again from client which was successful.
  I then install my AD in the RD with the domain controller virtual machine vmdc and promote it in to a domaine controller with a new forest 'mydomain.com".
Restarted and logged in to the vmdc as mydomain.com user. when to the ADUC and created two folders, -ADMINS and _EMPLOYEES respectively from which i created a user(Jane Doe) in the _AMIN folder and added to the domain admin group.
  Ithen login to vmdc RD as the domain admin user.
  I then Join Client to your domain (mydomain.com) and Setup Remote Desktop for non-administrative users on Client. Created a bunch of domain users and sign in to client with the domain users successfully
</p>

