# Help
## Command
```powershell
Get-Help $commandName
```
### Accepts Wildcards
```powershell
Get-Help *net* # Gets a list of Commands with net (Full Text Search)
```
### Flags
```powershell
Get-Help New-Alias -examples # Examples
Get-Help New-Alias -detailed 
Get-Help New-Alias -full
Get-Help New-Alias -online
```
### Get-Help Aliases
```powershell
help New-Alias
```
```powershell
man New-Alias
```
---
# Modules
## List Modules
```powershell
Get-Module -ListAvailable
```
## List Commands from Module
```powershell
Get-Command -Module NetAdapter 
```
---
# Commands
## Get info about Command
```powershell
Get-Command $commandName
```
### Accepts Wildcards and Verbs
#### Wildcard
```powershell
Get-Command *net* # Gets a list of commands with net in the name
```
#### Verbs
```powershell
Get-Command -Noun *net* -Verb Get # Can be used individually
```
Common Verbs:
- Get
- Set
- New
- Add
- Remove
- Read
##### Get a List of Verbs
```powershell
Get-Verb
```
---
# Parameters
```powershell
Show-Command $commandName
```
- Each Line is a parameter set and parameters can't be chosen from more than one.
- A square bracket around parameter means it's a positional argument.
- A square bracket after a parameter means it can accept more than one value.

---
# Tab Completion

Pressing Tab will show a list of possible commands based on what is entered. It also works with wildcards. For Example \*-service would display all commands with service in the name.

---
# About

The about flag displays information not about a command but about techniques or features.
## Complete list of Topics
```powershell
Get-Help about*
```
## Single Topic
```powershell
Get-Help about_CommonParameters
```
### Open in New Window
```powershell
Get-Help about_CommonParameters -ShowWindow
```