# Essential PowerShell for the Level 1 Helpdesk

PowerShell is a command-line and scripting tool that helps automate repetitive IT tasks. It allows users to manage systems, monitor performance, and improve workflow efficiency, making routine processes faster and reducing errors.

## Objective

This lab contains some beginner-friendly PowerShell scripts I learned and used in this project. The scripts cover real-world tasks such as troubleshooting network connectivity, restarting services, monitoring systems, and managing Active Directory accounts.
Even as a beginner, I wanted to build hands-on skills and share them publicly as part of my IT and Cybersecurity learning journey.

## Scripts Included

## Network Scripts

**Test-Network.ps1**

This script pings a list of hosts to check network connectivity.

`$hosts = @("google.com", "8.8.8.8", "9QUID-SERVER.9quid.local")  

foreach ($host in $hosts) {
    Write-Host "Testing connection to $host..."
    Test-Connection -ComputerName $host -Count 2 -ErrorAction SilentlyContinue |
    Select-Object Address, ResponseTime
}


## Services Scripts

**Restart-PrintSpooler.ps1**

This script restarts the Print Spooler service, commonly used to fix printer issues.

$service = "spooler"

Write-Host "Checking service: $service"
Get-Service -Name $service

Write-Host "Restarting $service..."
Restart-Service -Name $service -Force

Write-Host "$service restarted successfully."


## Active Directory Scripts

### Get-ADUserInfo.ps1

This script retrieves key information about a specific user from Active Directory.

Import-Module ActiveDirectory

### Prompt for the username

$userName = Read-Host -Prompt "Enter the username to look up"

# Get the user and select important properties

Get-ADUser -Identity $userName -Properties DisplayName, EmailAddress, LastLogonDate |
Select-Object Name, DisplayName, EmailAddress, LastLogonDate

### Get-ADUserGroupMembership.ps1

This script lists all the groups a specific user is a member of.This is essential for troubleshooting permissions issues.

### Import the Active Directory module

Import-Module ActiveDirectory

### Prompt for the username

$userName = Read-Host -Prompt "Enter the username to check group membership"

# Get the user's group memberships

Get-ADPrincipalGroupMembership -Identity $userName |
Select-Object Name

# Find-LockedOutUsers.ps1

This script finds all locked-out AD accounts.

Import-Module ActiveDirectory
Search-ADAccount -LockedOut | Select-Object Name, SamAccountName

**Unlock-User.ps1**

This script unlocks a user account in AD.

param(
    [Parameter(Mandatory=$true)]
    [string]$username
)

Import-Module ActiveDirectory
Unlock-ADAccount -Identity $username
Write-Host "User $username has been unlocked."

**Reset-Password.ps1**

This script resets a user password in AD.

param(
    [Parameter(Mandatory=$true)]
    [string]$username,
    
    [Parameter(Mandatory=$true)]
    [string]$newPassword
)

Import-Module ActiveDirectory
Set-ADAccountPassword -Identity $username -Reset -NewPassword (ConvertTo-SecureString $newPassword -AsPlainText -Force)
Write-Host "Password for $username has been reset."

**Get-GroupMembers.ps1**

This script lists members of an AD group.

param(
    [Parameter(Mandatory=$true)]
    [string]$groupName
)

Import-Module ActiveDirectory
Get-ADGroupMember -Identity $groupName | Select-Object Name, SamAccountName

## General Scripts

**Get-LoggedOnUser.ps1**

This script shows the currently logged-on user.

(Get-WmiObject -Class Win32_ComputerSystem).UserName

**Get-LastBootTime.ps1**

This script shows the last boot time of the system.

(Get-CimInstance Win32_OperatingSystem).LastBootUpTime

**Export-InstalledSoftware.ps1**

This script exports installed software list to a CSV.

$output = "C:\Temp\SoftwareList.csv"

Get-ItemProperty HKLM:\Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\* |
Select-Object DisplayName, DisplayVersion, Publisher |
Export-Csv $output -NoTypeInformation

Write-Host "Installed software exported to $output"

## Best Practices for the Helpdesk

- **Use `Get-Help`:** If you're unsure about a command, use `Get-Help`. For example, `Get-Help Get-ADUser -Examples` will show you how to use it.
- **Use `-WhatIf`:** For any command that makes a change (like `Unlock-ADAccount` or `Restart-Service`), you can add the `-WhatIf` parameter to see *what would happen* without actually doing it. This is a safe way to test your commands.
- **Start with "Get":** Most of your work will involve `Get-*` commands (`Get-ADUser`, `Get-Service`). These are read-only and safe to run. Be more cautious with `Set-*`, `Enable-*`, or `Remove-*` commands.
- **Don't Run as Admin Unnecessarily:** Many query commands don't require you to run PowerShell as an administrator. Only elevate your privileges when you need to make a change that requires it.
