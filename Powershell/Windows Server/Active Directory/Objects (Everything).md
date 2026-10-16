Is normally faster than specific object commands because there is no upfront filtering.
# New Object
```powershell
New-ADObject -Name $contactName -Type contact
```
## Common Parameters
|Parameter|Description|
|---|---|
|‑Name|Defines the name of an object|
|‑Type|Defines the LDAP type of an object|
|‑OtherAttributes|Defines properties of an object that isn't accessible from other parameters|
|‑Path|Defines the container in which an object is created|
# Modify Object
```powershell
Set-ADObject
```
# Display Object Properties
```powershell
Get-ADObject
```
# Delete Object
```powershell
Remove-ADObject
```
# Rename Object
```powershell
Rename-ADObject
```
# Restore Deleted Object
```powershell
Restore-ADObject
```
# Move Object
```powershell
Move-ADObject
```
# Sync Object Between DCs
```powershell
Sync-ADObject
```