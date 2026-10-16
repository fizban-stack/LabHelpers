# New OU
```powershell
New-ADOrganizationalUnit -Name Sales -Path "ou=marketing,dc=adatum,dc=com" -ProtectedFromAccidentalDeletion $true
```
## Common Parameters
|Parameter|Description|
|---|---|
|‑Name|Defines the name of a new OU|
|‑Path|Defines the location of a new OU|
|‑ProtectedFromAccidentalDeletion|Prevents anyone from accidentally deleting an OU; the default value is `$true`|
# Modify OU
```powershell
Set-ADOrganizationalUnit
```
# Display OU Properties
```powershell
Get-ADOrganizationalUnit
```
# Delete OU
```powershell
Remove-ADOrganizationalUnit
```