# Basic PowerShell Scripts for IT & Helpdesk

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

**Check-DNS.ps1**

This script checks if a hostname resolves correctly.

$hostname = "google.com"
Write-Host "Resolving DNS for $hostname..."
Resolve-DnsName -Name $hostname

## Services Scripts

**Restart-PrintSpooler.ps1**

This script restarts the Print Spooler service, commonly used to fix printer issues.

$service = "spooler"

Write-Host "Checking service: $service"
Get-Service -Name $service

Write-Host "Restarting $service..."
Restart-Service -Name $service -Force

Write-Host "$service restarted successfully."

**List-Stopped-Services.ps1**

This script lists all stopped services on the system.

Write-Host "Listing stopped services..."
Get-Service | Where-Object { $_.Status -eq "Stopped" } |
Select-Object Name, DisplayName, Status

## Monitoring Scripts

# Check-SystemInfo.ps1

This script displays basic system info like OS, CPU usage, and disk space.

Write-Host "=== System Info ==="
Get-ComputerInfo | Select-Object CsName, WindowsProductName, OsArchitecture

Write-Host "=== Top 5 CPU Processes ==="
Get-Process | Sort-Object CPU -Descending | Select-Object -First 5 Name, CPU

Write-Host "=== Disk Space ==="
Get-PSDrive -PSProvider FileSystem | Select-Object Name, Used, Free

**Monitor-DiskSpace.ps1**
# This script checks if disk space is running low.

$threshold = 5   # GB
$drive = Get-PSDrive C

$freeGB = [math]::Round($drive.Free/1GB, 2)
Write-Host "Drive C: Free Space = $freeGB GB"

if ($freeGB -lt $threshold) {
    Write-Warning "Low disk space! Less than $threshold GB free."
} else {
    Write-Host "Disk space is healthy."
}

## Active Directory Scripts

# Find-LockedOutUsers.ps1
# This script finds all locked-out AD accounts.

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


