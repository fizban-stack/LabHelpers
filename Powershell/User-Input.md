# Read-Host
```powershell
$answer = Read-Host "How old are you?"
```
## Without Trailing Colon
```powershell
Write-Host "How old are you? " -NoNewLine
$answer = Read-Host
```
## Without Displaying Answer
```powershell
$answer = Read-Host "How old are you?" -AsSecureString
```

# Selectable Option
```powershell
$selection = $users | Out-GridView -PassThru
```
## Outmode Options
|**Value**|**Description**|
|---|---|
|None|This is the default value that doesn't pass any objects further down the pipeline.|
|Single|This value allows users to select zero rows or one row in the **Out-GridView** window.|
|Multiple|This value allows users to select zero rows, one row, or multiple rows in the **Out-GridView** window. This value is equivalent to using the -PassThru parameter.|
# Parameters
## Declare Parameters
```powershell
Param(
	[string]$ComputerName ,
	[int]$EventID
)
```
### Default Values
```powershell
Param(
	[string]$ComputerName = "DC"
)
```
### Request User Input
```powershell
Param(
	[string]$ComputerName = Read-Host "Enter Computer Name"
)
```
### Boolean
Use Switch Type : Parameter Included == True
```powershell
Param(
	[switch]$quiet
)
```
## Use Parameters in Script
```powershell
.\GetEvent.ps1 -ComputerName DC -EventID 5772
```