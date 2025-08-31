# 1. Active Directory Domain services set-up

## 🎯 Objectives

- Install the Active Directory Domain Services (AD DS) role on Windows Server 2022.
- Promote the server to a Domain Controller a

## Steps and Walkthroughs

### Step 1 – Install Roles & Features

- Opened Server Manager, clicked on **Manage** selected **Add Roles and Features**

![alt text](<../2.AD DS Config/screenshots/01-roles & features.png>)
**Figure 01:** added roles and features

- Then completed the wizard and installed **AD DS**

![alt text](<../2.AD DS Config/screenshots/02-AD DS- installed.png>)
**Figure 02:** Shows the completed installation of AD DS

### Step 2 Promote Server to Domain Controller

After installing AD DS, I went on to promote the server to a Domain Controller.
> **Note:** At this stage, I took a snapshot of the system to preserve its current state before promotion.

![alt text](<../2.AD DS Config/screenshots/03-AD DS-promotion.png>)
**Figure 03:** server promotion

### Step 3 Verify Server has been promoted to Domain Controller

- At this stage after promoting the server to Domain Controller, the server rebooted and all modifications were applied successfully

![alt text](<../2.AD DS Config/screenshots/04-promoted-server.png>)
**Figure 12:** shows server as a domain controller
