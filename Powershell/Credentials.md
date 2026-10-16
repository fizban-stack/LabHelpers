# Prompt for Credentials
```powershell
$cred = Get-Credential
$command+parameters -Credential $cred
```
# Store Credentials
## User/Computer Specific Scope
```powershell
$cred = Get-Credential
$cred | Export-Clixml C:\cred.xml
```