# Introduction
This guide is for whomever is tired of testing the login flow due to the tiresome two-factor authentication step enforced by MitId.

The console app has only been tested against Signaturgruppens MitId broker.  

# Getting started:

### Step 1: Clone the repository

### Step 2: Build the solution and add a "mitid-users.txt" in the same directory as the executable. 

### Step 3: Add the following to your powershell profile: 
`Function runMitIdAuthenticator {cd C:\Tools\MitIdAuthenticator;  .\MitIdAuthenticator.exe @args}` 
`Set-Alias -Name mitid -Value runMitIdAuthenticator`

`Function openMitIdAuthenticatorSettings {cd C:\Tools\MitIdAuthenticator;  notepad.exe mitid_users.txt}`
`Set-Alias -Name mitid-settings -Value openMitIdAuthenticatorSettings`

**_OBS:_** The paths will have to be adjusted so that it actually points to the location of MitIdAuthenticator.exe 

_(If you don't have a powershell profile, then create one by adding a folder called "WindowsPowerShell" in "Documents" (da: "Dokumenter"). Inside "WindowsPowerShell" create a file called "Microsoft.PowerShell_profile.ps1". In this file, you add the two functions and two aliases above)._ 

### Step 4: Open a new powershell and run one of the following commands 
- `mitid` : Starts the MitIdAutoAuthenticator. 
- `mitid Theo404` : Starts the MitIdAutoAuthenticator and adds Theo404 to identities to auto authenticate. If the identity does not exist, it will be created. 
- `mitid-settings` : Shows the identies added in the current configuration. This is just a simple txt file. 
