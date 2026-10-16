***Aliases don't support parameters from original commands**
 
# Find Aliases
```powershell
Get-Alias $commandName
```
## Wildcards
```powershell
Get-Alias di* # Returns aliases with names that start with di
```
## Reverse from Alias
```powershell
Get-Alias -definition $commandName 
# Get-Alias -definition Remove-Item would return rd,erase, and ri
```
---
# Parameter Aliases
```powershell
Get-ChildItem -s # -s = Recurse
```
***Parameters can have aliases if you supply enough of the name for PowerShell to determine the parameter***

---
# New Aliases
```powershell
New-Alias -Name $alias $commandName
```