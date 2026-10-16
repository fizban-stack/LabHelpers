# New User
```powershell
New-ADUser -Name $userName -AccountPassword $password -Enabled $true
```
## Common Parameters
|Parameter|Description|
|---|---|
|‑AccountExpirationDate|Defines the expiration date for a user account|
|‑AccountPassword|Defines the password for a user account|
|‑ChangePasswordAtLogon|Requires a user account to change passwords at the next sign-in|
|‑Department|Defines the department for a user account|
|‑DisplayName|Defines the display name for a user account|
|‑HomeDirectory|Defines the location of the home directory for a user account|
|‑HomeDrive|Defines the drive letters that map to the home directory for a user account|
|‑GivenName|Defines the first name of a user account|
# Retrieve User
```powershell
Get-ADUser -Identity $userName 
```
## All Users and Properties
```powershell
Get-ADUser -Filter * -Properties *
```
## All Properties
```powershell
Get-ADUser -Identity $userName -Properties *
```
## Specific Properties
```powershell
Get-ADUser -Identity $userName -Properties $properties
```
# Modify User
```powershell
Set-ADUser
```
# Delete User
```powershell
Remove-ADUser
```
# Reset Password
```powershell
Set-ADAccountPassword
```
# Unlock Account
```powershell
Unlock-ADAccount
```
# Enable Account
```powershell
Enable-ADAccount
```
# Disable Account
```powershell
Disable-ADAccount
```