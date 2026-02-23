# -Windows-Client-Administration
Hyper‑V Infrastructure Setup

Created and configured multiple virtual switches (External + Private). 
Built two virtual machines: DC01 (Server 2019) and Wkstn01 (Windows 10/11).

Domain Controller Deployment (DC01)

Installed Windows Server 2019.
Set timezone, disabled Windows Firewall for setup tasks, and renamed NIC to External.
Installed Active Directory Domain Services, created a new forest/domain: yourname.com.
Configured a second NIC (Private) with static IP 172.16.0.1.
Installed, authorized, and configured DHCP with a functional IPv4 scope.
Installed and configured Windows Deployment Services (WDS) for network‑based OS installation.-

Windows Client Deployment (Wkstn01)

PXE‑booted the workstation and installed Windows 10 from WDS.
Switched the NIC to External and upgraded the OS to Windows 11.
Joined the device to the domain using static DNS pointed at DC01.
Installed Remote Server Administration Tools (RSAT).

Active Directory Management

Created a Marketing OU.
Created a domain user account Firstname.Lastname.
Created a Marketing Global Group and added the user to it.
Moved Wkstn01 into the Marketing OU.

Group Policy Implementation

Created and linked a Marketing Lockdown GPO to restrict Settings & Control Panel access.
Modified Default Domain Policy to enforce:

Complex passwords
Minimum length: 10 characters
Expiration every 30 days-FinalProject2-v3.4.docx&action=default&mobileredirect=true)



Client‑Side Administration

Verified lockdown settings.
Added domain user to local Administrators group.
Created + shared a folder with proper NTFS and Share permissions.
Created a system restore point.
Added a firewall rule exception for TCP 666 (DOOM traffic).
Enabled WinRM for remote PowerShell access.

Security & Reporting

Encrypted sensitive data using EFS.
Generated multiple system reports using PowerShell:

gpresult
Get-NetIPConfiguration
Get-NetFirewallRule
Get-ComputerRestorePoint
gwmi win32_product
and more…
