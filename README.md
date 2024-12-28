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

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/0c63e3c2-37dd-4754-ac98-0ba08a6cc039">

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

</details>

<details>

<summary>

### 2. ) 

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
