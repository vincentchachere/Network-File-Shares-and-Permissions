<br>

<p align="center">
<img width="700" src="https://github.com/user-attachments/assets/9b6b0a51-6411-4e01-96c5-1bb31e6fd986" alt="Microsoft Active Directory Logo"/>
<br>

<br>

<br>

<h1 align="center">File Shares and Permissions</h1> 
<br>

<p align="center">
<img src="https://github.com/user-attachments/assets/cf02aac9-bf41-43f0-890f-507ae51b4239" height="60%" width="60%" alt="9"/><br />
</p>
<br />

## Lab Overview

This lab builds on the previous one [here](https://github.com/vincentchachere/Active-Directory-Deployment-and-Configuration/edit/main/README.md). This lab guides users through creating file shares with specific permissions, testing access as different roles, and managing folder access using a security group in Active Directory. Participants will configure, test, and troubleshoot file share permissions to understand access control in a domain environment.

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- File sharing (Windows File Server)
- Permissions (Share and NTFS Permissions)
- Security Groups for Access Control
- PowerShell

## Operating Systems Used

- Windows Server 2022
- Windows 10 (21H2)

## High-Level File Shares and Permissions

- Create File Shares with Specific Permissions
- Test Access to File Shares as a Normal User
- Configure Security Groups, Assign Permissions, and Test Access

## Configuration Steps

<details>

<summary>

### 1. ) Create File Shares with Specific Permissions

</summary>

*Log into DC-1 as your domain admin account (mydomain.com\jane_admin)*

*Log into Client-1 as a normal user (mydomain.com\jib.soc)*

<ins>First, on DC-1 on the **C:\ drive**, create 4 folders</ins>:

- 1st Folder: `read-access`
- 2nd Folder: `write-access`
- 3rd Folder: `no-access`
- 4th Folder: `accounting`

*The folder names are arbitrary and chosen solely for simplicity in the lab.*

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/c1a30c85-ccd1-427f-a2da-a60297a773e5">

<br>
<br>
<br>

<ins>Set the following Permissions</ins>:

*Right-click each folder, select Properties to initiate setting groups and permissions, then follow the image from left to right.*

- Folder: **read-access**
  - Group: **Domain Users**
  - Permissions: **Read**

- Folder: **read-access**
  - Group: **Domain Users**
  - Permissions: **Read/Write**
 
- Folder: **read-access**
  - Group: **Domain Admins**
  - Permissions: **Read/Write**

- Skip **accounting** folder for now

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/aa3dce31-ad23-4945-94b1-8094e2d8bd04">

</details>

</details>

<details>

<summary>

### 2. ) Test Access to File Shares as a Normal User

</summary>

<ins>Log into Client-1 as normal user (mydomain.com\jib.soc) and navigate to the shared folders</ins>:

- Go To: `Start` > `run` > `\\dc-1`

- Access: the `read-access` folder

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/38b739d2-c152-4f64-9fb8-169cabf52eea">

<br>
<br>
<br>

<ins>Within the Read-Access Folder</ins>:



<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/b3af062d-cc32-497a-9ead-8d0740e6f6a1">

<br>
<br>
<br>

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/59bfdddc-8a6c-4296-9ac6-f80dda60bbff">

<br>
<br>
<br>

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/7be0b61a-dca1-44ba-9dd3-9020d3cc67ff">

<br>
<br>
<br>

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/5d7ae99a-be58-4114-a154-22a7e02d42ec">

<br>
<br>
<br>

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/4b996f16-ff1e-45eb-b0c4-a881a70d2b72">

</details>

<details>

<summary>

### 3. ) 

</summary>

<img width="800" alt="isolated" src="">

<br>
<br>
<br>

<img width="800" alt="isolated" src="">

<br>
<br>
<br>

<img width="800" alt="isolated" src="">

<br>
<br>
<br>

<img width="800" alt="isolated" src="">

<br>
<br>
<br>

<img width="800" alt="isolated" src="">

</details>
