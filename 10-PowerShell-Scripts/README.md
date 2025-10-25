# Essential PowerShell for the Level 1 Helpdesk

PowerShell is a command-line and scripting tool that helps automate repetitive IT tasks. It allows users to manage systems, monitor performance, and improve workflow efficiency, making routine processes faster and reducing errors.

## Objective

This lab contains some beginner-friendly PowerShell scripts I learned and used in this project. The scripts cover real-world tasks such as troubleshooting network connectivity, restarting services, monitoring systems, and managing Active Directory accounts.
Even as a beginner, I wanted to build hands-on skills and share them publicly as part of my IT and Cybersecurity learning journey.

## The Essential Commands

### 1. `Get-Help`
This is the most important command in PowerShell. It's the built-in instruction manual for everything else.

*   **What it does:** Provides detailed information, including descriptions, parameters, and examples for any PowerShell command.
*   **When I use it:** Before trying any new command, or when I forget how a command works.
*   **Example:**
    ```powershell
    # Get the full manual for the Get-Service command
    Get-Help Get-Service

    # Show just the practical examples for Get-Service
    Get-Help Get-Service -Examples
    ```

### 2. `Get-Service`
A core command for investigating issues with applications or Windows features that run in the background.

*   **What it does:** Gets the status of services on a local or remote computer.
*   **When I use it:** When a user reports that an application (like a printer) isn't working, I use this to check if the required service is "Running" or "Stopped".
*   **Example:**
    ```powershell
    # Check the status of the Print Spooler on a user's machine named "PC-123"
    Get-Service -Name spooler -ComputerName PC-123
    ```

### 3. `Restart-Service`
The go-to command for the classic "turn it off and on again" fix for a frozen service.

*   **What it does:** Stops and then starts a service.
*   **When I use it:** If a service is "Running" but still not working correctly, a restart often resolves the issue.
*   **Example:**
    ```powershell
    # Restart the Print Spooler service on the local machine
    Restart-Service -Name spooler -Force
    ```

### 4. `Test-Connection`
The PowerShell equivalent of `ping`. It's the first step for any network-related problem.

*   **What it does:** Sends a network packet to another machine to see if it's online and reachable.
*   **When I use it:** When a user says they "can't access the server" or "the internet is down," I use this to check connectivity to a known target like a server or a public DNS.
*   **Example:**
    ```powershell
    # Send 2 pings to Google's public DNS server to test internet connectivity
    Test-Connection -ComputerName 8.8.8.8 -Count 2
    ```

### 5. `Get-ADUser`
The starting point for almost any user-related issue in a domain environment.

*   **What it does:** Retrieves information about a user from Active Directory.
*   **When I use it:** To check a user's account details, such as their full name, email address, or if their account is locked out.
*   **Example:**
    ```powershell
    # Get all available information for the user 'jsmith'
    Get-ADUser -Identity jsmith -Properties *
    ```

### 6. `Unlock-ADAccount`
One of the most common helpdesk tasks.

*   **What it does:** Unlocks a user's Active Directory account.
*   **When I use it:** When a user calls because they are locked out after too many incorrect password attempts.
*   **Example:**
    ```powershell
    # Unlock the account for the user 'jsmith'
    Unlock-ADAccount -Identity jsmith
    ```

### 7. `Get-Process`
Useful for finding out what's running on a user's machine, especially if it's slow.

*   **What it does:** Shows all the processes currently running on a computer.
*   **When I use it:** To identify applications that are using too much memory or CPU, or to find and terminate a frozen program.
*   **Example:**
    ```powershell
    # Find all running Chrome processes and sort them by CPU usage (highest first)
    Get-Process -Name chrome | Sort-Object CPU -Descending
    ```

### 8. `Get-EventLog`
The detective's tool. It lets you read the logs that Windows creates for everything that happens.

*   **What it does:** Retrieves events from the Windows Event Logs.
*   **When I use it:** To investigate the root cause of an application crash or a system error by looking for recent error entries.
*   **Example:**
    ```powershell
    # Show the 20 most recent 'Error' entries from the System log
    Get-EventLog -LogName System -Newest 20 -EntryType Error
    ```
