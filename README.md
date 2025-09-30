# Windows Server 2022 Homelab: From Bare Metal to a Fully Functioning Enterprise Environment

This project documents the creation of a complete, small-business IT infrastructure from the ground up in a virtualized environment. Starting with a single Windows Server 2022 instance, I designed, built, and secured a full-featured network, including:

- **Core Infrastructure:** Active Directory, DNS, and DHCP.
- **Client Management:** Onboarding of Windows and Linux clients.
- **Security:** Group Policies, a Public Key Infrastructure (PKI) with AD CS, and patch management with WSUS.
- **IT Operations:** A live helpdesk ticketing system (osTicket) and a toolkit of essential PowerShell scripts.


## Core Competencies Demonstrated

This project showcases hands-on experience across several key areas of IT infrastructure and support:

#### 1. Identity & Access Management (IAM)

- Deployed Active Directory Domain Services (AD DS) to serve as the central identity provider.
- Managed users, groups, and Organizational Units (OUs) for role-based access control.
- Implemented Group Policy Objects (GPOs) to enforce password policies, account lockouts, and deploy software and settings.
- Integrated an Ubuntu Desktop client into the domain, demonstrating cross-platform authentication with Kerberos and SSSD.

#### 2. Network Services & Security

- Configured and managed DNS (forward and reverse lookup zones) and DHCP (scopes, reservations, exclusions).
- Deployed a Public Key Infrastructure (PKI) using Active Directory Certificate Services (AD CS) to issue SSL/TLS certificates for internal services.
- Hosted a secure internal website on IIS, including binding the SSL certificate.
- Implemented Windows Server Update Services (WSUS) for centralized patch management and staged update rollouts.

#### 3. IT Operations & Service Management

- Deployed and configured an osTicket helpdesk system on a full LAMP-like stack (IIS, MySQL, PHP).
- Simulated the entire IT support ticket lifecycle, from user submission to agent resolution.
- Developed a toolkit of practical PowerShell scripts for common Level 1 Helpdesk tasks like user lookups and unlocking accounts.

#### 4. Storage & Resource Management

- Configured a file server with departmental shares, enforcing permissions using the principle of least privilege.
- Deployed network printers and managed them centrally via Print Services.
- Implemented a disaster recovery plan using Windows Server Backup.

### Course Reference:

This lab follows concepts from **Introduction to Windows Server 2016 for Beginners** by Alton, focusing on AD DS setup, DNS/DHCP configuration, User Access Management and core server management.

## Security Skills Gained

- **Identity & Access Management (IAM):** Managed users, groups, and OUs; enforced password policies and account lockouts to protect against unauthorized access.  
- **Patch Management & Endpoint Security:** Configured WSUS to deploy updates and reduce vulnerabilities across domain-joined clients.  
- **Service & Network Hardening:** Secured IIS web services and intranet communication using certificates issued by AD CS.  
- **Policy Implementation & Compliance:** Applied Group Policy Objects (GPOs) to enforce security standards and organizational policies.  
- **Foundational PKI & Encryption Knowledge:** Installed and configured Active Directory Certificate Services, issued domain certificates, and learned certificate-based authentication for secure internal communications.  

## General IT Skills Gained

- **System Installation & Configuration:** Windows Server 2022, Windows 11 clients, DNS, DHCP, IIS, AD CS.  
- **Active Directory & User Management:** Users, groups, OUs, permissions, role-based access.  
- **Networking & Troubleshooting:** DNS, DHCP, connectivity, domain join issues.  
- **File & Print Services Management:** Shared folders, NTFS permissions, network printers  
- **Automation & Scripting:** Basic PowerShell for repetitive tasks and user management.  
- **Cross-Platform Awareness:** Ubuntu Desktop AD exploration  
- **Documentation & Organization:** Maintaining configs, screenshots, and structured lab files.  
- **Problem-Solving:** Diagnosing and resolving network, authentication, and service issues.

### Downloads & Resources

**Operating Systems** (official sources recommended):

- [Windows Server 2022](https://go.microsoft.com/fwlink/p/?linkid=2195333).  
- [Windows 11](https://www.microsoft.com/en-us/software-download/windows11). 
- [Ubuntu Desktop](https://ubuntu.com/download/desktop/thank-you?version=24.04.3&architecture=amd64&lts=true).

**Virtualization Software:**  
- [VMware Workstation Pro](https://support.broadcom.com/group/ecx/productdownloads?subfamily=VMware%20Workstation%20Pro&freeDownloads=true).  
  *Requires a free Broadcom (VMware) account.*


### Repository Structure

The project is organized into step-specific folders containing screenshots, scripts, or configuration files for each lab task.

### Lab Environment

| Device/VM | OS                  | Role                                 |
|-----------|-------------------|-------------------------------------|
| Server    | Windows Server 2022 | Domain Controller (AD DS, DNS, DHCP) |
| Client 1  | Windows 11          | Domain-joined workstation            |
| Client 2  | Ubuntu Desktop      | Linux client Intergration        |

### Linux Client Intergration

 An Ubuntu Desktop client was included in the lab as a curiosity-driven, exploratory exercise to see how a Linux system could interact with Active Directory.

 The goal was to explore cross-platform concepts and gain a better understanding of how non-Windows clients could fit into a domain environment. I aim to improve these skills in the future as I gain more experience.

### Network Diagram

![alt text](<Docs/WinServer_AD.drawio (3).png>)

# Table of Contents

## Table of Contents

| Lab # | Title                                       | Core Concepts Covered                                 |
|-------|---------------------------------------------|-------------------------------------------------------|
| 01    | [Server Setup](./01-Server-Setup/)                                | VM Creation, OS Install, Basic Networking             |
| 02    | [Active Directory Setup](./02-Active-Directory-Setup/)                      | AD DS, Domain Controller Promotion, OUs               |
| 03    | [DNS and DHCP Configuration](./03-DNS-and-DHCP-Configuration/)                  | Forward/Reverse Lookups, DHCP Scopes                  |
| 04    | [User Access Management](./04-User-Access-Management/)                      | Users, Groups, GPOs                                   |
| 05    | [Windows 11 AD Join](./05-Windows11-AD-Join/)                          | Domain Join, Client Verification                      |
| 06    | [File Server Management](./06-File-Server-Management/)                      | Share/NTFS Permissions, Mapped Drives                 |
| 07    | [IIS and Print Services](./07-IIS-and-Print-Services-Configuration/)                      | Web Server, PKI, SSL, Print Management                |
| 08    | [WSUS and Windows Backup Lab](./08-WSUS-and-Windows-Backup-Lab/)                 | Patch Management, Disaster Recovery                   |
| 09    | [Ubuntu AD Integration](./09-Ubuntu-AD-Intergration/)                       | SSSD, Kerberos, Cross-Platform Auth                   |
| 10    | [PowerShell Scripts](./10-PowerShell-Scripts/)                          | Automation, Helpdesk Efficiency                       |
| 11    | [osTicket Helpdesk](./11-osTicket-Helpdesk/)                           | ITSM, Ticketing Systems, Web Stack Deployment         |

**Each folder contains screenshots and resources relevant to that step.**
