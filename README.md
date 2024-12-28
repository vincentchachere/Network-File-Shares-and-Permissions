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

As a domain user, the permissions set earlier will prevent you from creating new text documents (or folders).

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/59bfdddc-8a6c-4296-9ac6-f80dda60bbff">

<br>
<br>
<br>

<ins>Testing Write-Access Folder</ins>:

Now we can try doing the same with the write-access folder, so head inside there.

*Any guesses on what will happen when trying to create a text document (or folder) inside here?*

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/7be0b61a-dca1-44ba-9dd3-9020d3cc67ff">

<br>
<br>
<br>

<ins>Testing Write-Access Folder</ins>:

Right-click an empty space to **create a new text document**, **add text**, and **try saving it**.

*This works because the folder's permissions are set to read/write for domain user accounts.*

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/5d7ae99a-be58-4114-a154-22a7e02d42ec">

<br>
<br>
<br>

<ins>Testing no-Access Folder</ins>:

Finally, if you try to enter the **no-access** folder your access will be denied, since the permissions are set to read/write exclusively for domain admin accounts, not domain users.

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/4b996f16-ff1e-45eb-b0c4-a881a70d2b72">

</details>

<details>

<summary>

### 3. ) Configure Security Groups, Assign Permissions, and Test Access

</summary>

Go back to DC-1, in Active Directory, and create a Security Group called "**ACCOUNTANTS**".

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/d891e3a7-e104-42da-8d29-6ce5cca11fbe">

<br>
<br>
<br>

<ins>Configure Security Groups, Assign Permissions, and Test Access</ins>:

On the "accounting" folder you created earlier, set the following permissions:

- Folder: "**accounting**"
  - Group: "**ACCOUNTANTS**"
  - Permissions: "**Read/Write**"

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/a3f67c58-8960-4863-9a82-017c39d581ab">

<br>
<br>
<br>

<ins>Configure Security Groups, Assign Permissions, and Test Access</ins>:

On Client-1, as a normal user (mydomain.com\jib.soc), **try to access the accountants folder**. It should fail.

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/887a3350-a53d-4a11-8430-00f40e003e37">

<br>
<br>
<br>

<ins>Configure Security Groups, Assign Permissions, and Test Access</ins>:

On DC-1, **make your domain user account a member of** the "**ACCOUNTANTS**" Security Group.

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/b09de8f1-a0e7-4592-a5c9-f9b2c44c02df">

<br>
<br>
<br>

<ins>Configure Security Groups, Assign Permissions, and Test Access</ins>:

Sign back into Client-1 as your domain user account (mydomain.com\jib.soc) and try to access the "accounting" share file in **\\\dc-1**.

*You may need to restart your Client-1 VM from your Azure Portal.*

*Does it work now?*

<img width="800" alt="isolated" src="https://github.com/user-attachments/assets/a58f9c99-e467-43ed-9692-2b456e521c6c">

</details>
