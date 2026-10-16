# Create New GPO
```powershell
New-GPO -Name "IT Team GPO" -StarterGPOName "IT Starter GPO"
```
# Display GPO Properties
```powershell
Get-GPO
```
# Modify GPO Properties
```powershell
Set-GPO
```
# Delete GPO
```powershell
Remove-GPO
```
# Rename GPO
```powershell
Rename-GPO
```
# Backup GPO
```powershell
Backup-GPO
```
# Copy GPO
```powershell
Copy-GPO
```
# Restore GPO from Backup
```powershell
Restore-GPO
```
# Link GPO to Container
```powershell
New-GPLink -Name "IT Team GPO" -Target "OU=IT,DC=adatum,DC=com"
```
# Import GPO to Container
```powershell
Import-GPO
```
# Configure Registry-based GPO Settings
```powershell
Set-GPRegistryValue
```
