# Windows Server 2022 Lab: Active Directory & Core IT Services

This project simulates a small organizational network to gain hands-on experience with Windows Server 2022 administration, Active Directory Domain Services (AD DS), DNS/DHCP configuration, file and print services, and PowerShell automation. Completed in a personal virtual lab environment, it demonstrates practical skills in user and group management, network configuration, and troubleshooting, all of which are applicable to entry-level IT and helpdesk roles.

## Project Objectives / Skills Demonstrated

This project showcases practical experience with the following:

- Configured **Windows Server 2022** and promoted a **Domain Controller**  
- Implemented **Active Directory Domain Services (AD DS), DNS, and DHCP** for a small network  
- Created and managed **users, groups, and organizational units (OUs)**  
- Joined a **Windows 11 client** to the domain  
- Configured **file shares, Group Policies, IIS web services, and print services**  
- Automated routine tasks using **PowerShell scripts**  
-Explored optional **Ubuntu Desktop integration** to learn cross-platform authentication  
- Practiced **network troubleshooting and IT support skills**  


### Course Reference:
This lab follows concepts from **Introduction to Windows Server 2016 for Beginners** by Alton, focusing on AD DS setup, DNS/DHCP configuration, User Access Management and core server management.


## Security Skills Gained

- **Identity & Access Management (IAM):** Managed users, groups, and OUs; enforced password policies and account lockouts to protect against unauthorized access.  
- **Patch Management & Endpoint Security:** Configured WSUS to deploy updates and reduce vulnerabilities across domain-joined clients.  
- **Service & Network Hardening:** Secured IIS web services and intranet communication using certificates issued by AD CS.  
- **Policy Implementation & Compliance:** Applied Group Policy Objects (GPOs) to enforce security standards and organizational policies.  
- **Foundational PKI & Encryption Knowledge:** Installed and configured Active Directory Certificate Services, issued domain certificates, and learned certificate-based authentication for secure internal communications.  

## General IT Skills Gained

- **System Installation & Configuration:** Windows Server 2022, Windows 11 clients, DNS, DHCP, IIS, AD CS  
- **Active Directory & User Management:** Users, groups, OUs, permissions, role-based access  
- **Networking & Troubleshooting:** DNS, DHCP, connectivity, domain join issues  
- **File & Print Services Management:** Shared folders, NTFS permissions, network printers  
- **Automation & Scripting:** PowerShell for repetitive tasks and user management  
- **Cross-Platform Awareness:** Ubuntu Desktop AD exploration  
- **Documentation & Organization:** Maintaining configs, screenshots, and structured lab files  
- **Problem-Solving:** Diagnosing and resolving network, authentication, and service issues

### Downloads & Resources

**Operating Systems** (official sources recommended):

- [Windows Server 2022](https://go.microsoft.com/fwlink/p/?linkid=2195333)  
- [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) 
- [Ubuntu Desktop](https://ubuntu.com/download/desktop/thank-you?version=24.04.3&architecture=amd64&lts=true)

**Virtualization Software:**  
- [VMware Workstation Pro](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro&freeDownloads=true)  
  *Requires a free Broadcom (VMware) account.*


### Repository Structure

The project is organized into step-specific folders containing screenshots, scripts, or configuration files for each lab task:<br />

### Lab Environment

| Device/VM | OS                  | Role                                 |
|-----------|-------------------|-------------------------------------|
| Server    | Windows Server 2022 | Domain Controller (AD DS, DNS, DHCP) |
| Client 1  | Windows 11          | Domain-joined workstation            |
| Client 2  | Ubuntu Desktop      | Linux client (exploratory)        |

### Linux Client Exploration

 An Ubuntu Desktop client was included in the lab as a curiosity-driven, exploratory exercise to see how a Linux system could interact with Active Directory.

 This was not part of core lab requirements, and I am still learning about Linux integration. The goal was to explore cross-platform concepts and gain a better understanding of how non-Windows clients could fit into a domain environment. I aim to improve these skills in the future as I gain more experience.

### Network Diagram

![alt text](<Docs/WinServer_AD.drawio (2).png>)

# Table of Contents

1. [Server Setup](01-server-setup)
2. [Active Directory Setup](#02-active-directory-setup)
3. [DNS and DHCP Configuration](#03-dns-and-dhcp-configuration)
4. [User Access Management](#04-user-access-management)
5. [Windows 11 AD Join](#05-windows11-ad-join)
6. [File Server Management](#06-file-server-management)
7. [IIS and Print Services Configuration](#07-iis-and-print-services-configuration)
8. [WSUS and Windows Backup Lab](#08-wsus-and-windows-backup-lab)
9. [Ubuntu AD Integration](#09-ubuntu-ad-integration)
10. [PowerShell Scripts](#10-powershell-scripts)

**Each folder contains screenshots and resources relevant to that step.**
