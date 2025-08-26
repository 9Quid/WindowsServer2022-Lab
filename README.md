# Active Directory Lab - Windows Server 2022

This was the very first project in my journey into the world of IT. I’ve practiced it many times, both by following online tutorials and by trying it on my own. Some days everything works smoothly, and other days leave you scratching your head—especially when it comes to network connectivity. But that’s all part of the journey, and I’m gradually embracing it, and you should too!. <br />

## Overview & Lab Goals

This project simulates a small organizational network to practice Active Directory management. Key objectives:

- Install and configure Windows Server 2022
- Set up Active Directory Domain Services (AD DS), DNS, and DHCP
- Create and manage users, groups, and organizational units (OUs)
- Join a Windows 11 client to the domain
- Optionally join Ubuntu Server/Desktop and Kali Linux clients
- Configure network file shares and basic Group Policies


### Course Reference:
This lab follows concepts from *Introduction to Windows Server 2016 for Beginners* by Alton, focusing on AD DS setup, DNS/DHCP configuration, and core server management.


### Skills Gained

- **Windows Server Administration:** Installing and configuring Windows Server 2022  
- **Active Directory Management:** Users, groups, OUs, client joins  
- **Networking Services:** DNS and DHCP configuration for domain clients  
- **Identity & Access Management:** Permissions, password resets, and Group Policies  
- **Cross-Platform Integration (Optional):** Ubuntu and Kali clients in AD  
- **IT Support & Troubleshooting:** Resolving authentication and network issues  
- **Virtualization:** Using VMware for lab environments

### Downloads & Resources

**Operating Systems** (official sources recommended):

- [Windows Server 2022](https://go.microsoft.com/fwlink/p/?linkid=2195333)  
- [Windows 11](https://www.microsoft.com/en-us/software-download/windows11)  
- [Kali Linux](https://www.kali.org/get-kali/#kali-installer-images)  
- [Ubuntu Server](https://ubuntu.com/download/server)  
- [Ubuntu Desktop](https://ubuntu.com/download/desktop/thank-you?version=24.04.3&architecture=amd64&lts=true)

**Virtualization Software:**  
- [VMware Workstation Pro](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro&freeDownloads=true)  
  *Requires a free Broadcom (VMware) account.*


### Repository Structure

The project is organized into step-specific folders containing screenshots, scripts, or configuration files for each lab task:<br />

AD-Lab-Windows-Server-2022/ <br />
├─ README.md <br />
├─ 01-Server-Setup/ <br />
├─ 02-AD-DS-Config/ <br />
├─ 03-DNS-DHCP/ <br />
├─ 04-Users-Groups/ <br />
├─ 05-Clients/ <br />
├─ 06-File-Share-GPO/ <br />
├─ 07-Linux-Integration/ <br />
└─ 08-Lessons-Learned/ <br />

***Each folder contains screenshots and resources relevant to that step.***


### Lab Environment
| Device/VM | OS                  | Role                                 |
|-----------|-------------------|-------------------------------------|
| Server    | Windows Server 2022 | Domain Controller (AD DS, DNS, DHCP) |
| Client 1  | Windows 11          | Domain-joined workstation            |
| Client 2  | Ubuntu Server       | Optional Linux domain client         |
| Client 3  | Ubuntu Desktop      | Optional Linux domain client         |
| Client 4  | Kali Linux          | Optional Linux domain client         |
