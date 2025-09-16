# Active Directory Domain services set-up

## Introduction

In this lab, I set up Active Directory Domain Services on Windows Server 2022. I installed the AD DS role, promoted the server to a Domain Controller, and verified functionality by creating and testing an Organizational Unit (OU).

## Objectives

The goal of this lab was to install and configure Active Directory Domain Services (AD DS), promote the server to a Domain Controller, and confirm its functionality in the domain environment..

### Step 1: Install Roles & Features

- Opened Server Manager, clicked on `Manage` selected `Add Roles and Features`.

![alt text](<../2.AD DS Config/screenshots/01-roles & features.png>)

**Figure shows added roles and features**

- Then completed the wizard and installed `AD DS`.

![alt text](<../2.AD DS Config/screenshots/02-AD DS- installed.png>)

**Figure Shows the completed installation of AD DS**

### Step 2: Promote Server to Domain Controller

After installing AD DS, I went on to promote the server to a Domain Controller.
> **Note:** At this stage, I took a snapshot of the system to preserve its current state before promotion.

![alt text](<../2.AD DS Config/screenshots/03-AD DS-promotion.png>)

**Figure server promotion**

### Step 3: Verify Server has been promoted to Domain Controller

- At this stage after promoting the server to Domain Controller, the server rebooted and all modifications were applied successfully.

![alt text](<../2.AD DS Config/screenshots/04-promoted-server.png>)

**Figure shows server as a domain controller**

### Step 4: Test Domain Controller Functionality

To ensure the Domain Controller is fully working , I created an Organizational Unit as seen below.

![alt text](<../2.AD DS Config/screenshots/05-TestOU.png>)

**Figure shows a test OU**

## Useful Commands

### Verify Domain Controller Installation (PowerShell)

- `Get-ADDomain`
- `Get-ADForest`

![alt text](<../2.AD DS Config/screenshots/06.DC-functionality.png>)

**Figure shows DC fully functioning**

### Lessons Learned

- Snapshots are your best friend. Take regular snapshots to save rollback in case of any misconfigurations.

- DNS is tightly integrated: AD DS setup automatically installs/configures DNS, and allows promotion to be successfull.

- After promotion a reboot is mandatory.

- OU creation is a quick test. Creating an OU  is a simple way to confirm DC is working properly.

- Patience during promotion. The wizard takes a while and can look stuck but letting it finish is the way to go.
