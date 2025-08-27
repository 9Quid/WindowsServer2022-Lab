# Active Directory Lab - Windows Server 2022

This was the very first project in my journey into the world of IT. I’ve practiced it many times, both by following online tutorials and by trying it on my own. Some days everything works smoothly, and other days leave you scratching your head especially when it comes to network connectivity. But that’s all part of the journey, and I’m gradually embracing it, and you should too!. <br />

## Overview & Lab Goals

This project simulates a small organizational network to practice Active Directory management. Key objectives:

- Installed and configure Windows Server 2022
- Set up Active Directory Domain Services (AD DS), DNS, and DHCP
- Create and manage users, groups, and organizational units (OUs)
- Joined a Windows 11 client to the domain
- Optionally join Ubuntu Server/Desktop and Kali Linux clients
- Configured network file shares and basic Group Policies


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

**ActiveDirectory-Lab-WS2022/**

**├─ docs/<br />**
&nbsp;&nbsp;&nbsp;&nbsp;└─ network-diagram.png

README.md      
**[1. Server-Setup/](./1.Server-Setup/README.md) <br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md                
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/          
&nbsp;&nbsp;&nbsp;&nbsp; ├─ server-install.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ server-nic.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ roles-features.png<br />

**[2. AD DS Config/](./2.AD-DS-Config/README.md) <br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md                 
&nbsp;&nbsp;&nbsp;&nbsp;├─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─dc-promotion.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ ad-ds-config.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ ad-users-groups.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;└─ configs/<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ ad-ds-backup.txt<br />

**[3. DNS & DHCP Config/](./3.DNS-DHCP/README.md)<br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md                
&nbsp;&nbsp;&nbsp;&nbsp;├─ dhcp-config-export.txt<br />
&nbsp;&nbsp;&nbsp;&nbsp;├─ dns-zone-export.txt<br />
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ server-nic.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ dhcp-scope.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ dns-zone.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  └─ nslookup.png<br />

**[4. Users, Groups & OUs Config/](./4.Users-Groups-OUs/README.md)<br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md           
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ ou-structure.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ group-membership.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  └─ delegated-permissions.png<br />

**[5. Windows 11/](./5.Windows-11-client/README.md)/<br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md           
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ win11-join.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ win11-dhcp.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ win11-nslookup.png<br />

**[6. File Share & GPO/](./6.File-Share-GPO/README.md)<br />**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md             
&nbsp;&nbsp;&nbsp;&nbsp;├─ configs/<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ gpo-export.txt<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ file-share.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ gpo-desktop-bg.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ gpo-logon-banner.png<br />

**[7. IIS & Print Services/<br />](./7.IIS-Print-Services/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md              
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ iis-install.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ website-config.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ printer-deploy.png<br />

**[8.FRSM-Quotas/<br />](./8.FRSM-Qoutas/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md             
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ fsrm-setup.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ user-quotas.png<br />

**[9.RDP-WSUS-Backup/<br />](./9.RDP,WSUS,Backup/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md     
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ rdp-config.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; ├─ wsus-console.png<br />
&nbsp;&nbsp;&nbsp;&nbsp; └─ backup-snapshot.png<br />

**[10. PowerShell Scripts/<br />](./10.PowerShell-Scripts/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md            
&nbsp;&nbsp;&nbsp;&nbsp;└─ scripts/<br />
&nbsp;&nbsp;&nbsp;&nbsp;├─ add-ad-user.ps1<br />
&nbsp;&nbsp;&nbsp;&nbsp;├─ manage-groups.ps1<br />
&nbsp;&nbsp;&nbsp;&nbsp;  └─ manage-ous.ps1<br />

**[11. Linux Clients/<br />](./11.linux-Clients/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─ README.md             
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/<br />
&nbsp;&nbsp;&nbsp;&nbsp;  ├─ ubuntu-join.png<br />
&nbsp;&nbsp;&nbsp;&nbsp;  └─ kali-testing.png<br />

**[12. Lessons Learned/<br />](./12.Lessons-Learned/README.md)**
&nbsp;&nbsp;&nbsp;&nbsp;├─README.md                 
&nbsp;&nbsp;&nbsp;&nbsp;└─ screenshots/            
&nbsp;&nbsp;&nbsp;&nbsp; └─ example-issue.png


***Each folder contains screenshots and resources relevant to that step.***


### Lab Environment
| Device/VM | OS                  | Role                                 |
|-----------|-------------------|-------------------------------------|
| Server    | Windows Server 2022 | Domain Controller (AD DS, DNS, DHCP) |
| Client 1  | Windows 11          | Domain-joined workstation            |
| Client 2  | Ubuntu Server       | Optional Linux domain client         |
| Client 3  | Ubuntu Desktop      | Optional Linux domain client         |
| Client 4  | Kali Linux          | Optional Linux domain client         |
