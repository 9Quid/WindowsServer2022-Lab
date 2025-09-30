# Joining a Windows Client to the Domain

## Introduction

In this lab, I deployed a Windows 11 client and joined it to the `9quid.local` Active Directory domain. This process enables centralized management, allowing the client to authenticate users via the Domain Controller and receive policies enforced by GPOs.

**Domain Join:** The process of connecting a computer to an Active Directory domain so it becomes part of a centrally managed network.

## Objective

The goal of this lab was to join a Windows client machine to the Active Directory domain, verify that domain user accounts could log in, and confirm that Group Policies were applied successfully.

### Step 1: Install Windows 11

Installed Windows 11 Pro on VMware with `4 GB RAM`, `2 CPUs`, and `64 GB disk`.

![alt text](<screenshots/01-Win11-vmware-resource-allocation - Copy.png>)

***The figure above shows the set-up in vmware***

Next, I selected `Windows 11 Pro for workstation`.

![alt text](<screenshots/02-win11-version-installation - Copy.png>)

***The figure above shows the win11 version***

I then completed the installation setup and confirmed the client booted successfully.

![alt text](<screenshots/04-win11-installed - Copy.png>)

***The figure above shows win11 successully installed***

### Step 2: Configure Network Settings

Crucially, I configured the client’s primary DNS server to be the IP address of the Domain Controller (`192.168.1.9`). This allows the client to resolve the domain name and locate the DC for authentication.

![alt text](<screenshots/07-win11-dns-config - Copy.png>)

***The figure above shows dns settings***

I verified connectivity using ping `192.168.1.9` and ping `9quid.local`.

![alt text](screenshots/14.successfull-communication-with-DC.png)

***The figure above shows successfull communication with DC***

### Step 3: Join Client to the Domain

I opened `System Properties` -> `Changed Computer Name` to `9Quid-11` -> selected Domain.

![alt text](<screenshots/08-joined-workgroup to DC - Copy.png>)

***The figure above shows successful name change***

I entered `9quid.local` and authenticated with the Domain Admin account.

![alt text](<screenshots/09-successfully-joined-DC - Copy.png>)

***The figure above shows win11 has been joined successfully***

I restarted the machine to complete the domain join.

### Step 4: Verify Domain Login

At the login screen, I selected Other user and signed in with domain account `9quid\cbrest`.

I confirmed the login was successful and profile created.

![alt text](screenshots/15.user-log-in.png)

***The figure above shows successful log in***

### Step 5: Test Group Policy Application

- I ran `gpupdate /force` to refresh policies.

- I then confirmed that `Control Panel restrictions` and `logon banner` appeared as configured in previous chapters.

![alt text](screenshots/19-confirmed-logon-banner.png)

***The figure above shows group policy was applied***

### Key Settings

- Configured the client to use the Domain Controller’s Host-Only IP as its DNS server.

- Verified network connectivity by pinging the Domain Controller.

- Joined the client machine to the domain via System Properties.

- Rebooted the client and logged in with a domain user account.

### Troubleshooting

- I checked DNS if client failed to join the domain, client must use DC’s DNS, not external DNS.

- Verified that the DC and client were on the same Host-Only network.

- Used `nltest /dsgetdc:9quid.local` to confirm the client could locate the Domain Controller.

### Lessons Learned

- DNS is non-negotiable. The client *must* use the Active Directory DNS server to resolve the domain name. Without it, the domain join will fail because the client cannot locate the DC.

- Always confirm the client is getting its IP and DNS from the DHCP scope on the DC.

- GPOs are applied on login. It was satisfying to see the logon banner and other policies apply automatically, demonstrating the power of centralized management.
