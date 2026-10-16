# New Computer Account
```powershell
New-ADComputer -Name $computerName -Path "ou=marketing,dc=adatum,dc=com" -Enabled $true
```
## Common Parameters
|Parameter|Description|
|---|---|
|`-Name`|Defines the name of a computer account|
|`-Path`|Defines the OU or container where a computer account is created|
|`-Enabled`|Defines whether the computer account is enabled or disabled; by default, a computer account is enabled, and a random password is generated|
# Modify Computer Account
```powershell
Set-ADComputer
```
# Display Computer Properties
```powershell
Get-ADComputer
```
# Delete Computer Account
```powershell
Remove-ADComputer
```
# Verify or Repair Trust Relationship
***Only Available in PowerShell 5.1***
```powershell
Test-ComputerSecureChannel
```
## Repair Trust
***Run on Computer with Broken Trust***
```powershell
Test-ComputerSecureChannel -Repair
```
# Reset Computer Account Password
***Only Available in PowerShell 5.1***
```powershell
Reset-ComputerMachinePassword
```