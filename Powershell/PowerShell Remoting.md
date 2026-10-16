# Single Command
```powershell
Invoke-Command -FilePath $script -ComputerName $remoteComputer
```
```powershell
Invoke-Command -ComputerName $remoteComputer -Credential $username -ScriptBlock {$commands}
```
## On Multiple Computers
```powershell
$computers = New-PSSession –ComputerName $computerName,$computerName
Invoke-Command –Session $computers –ScriptBlock { $command }
```
## Using a List of Computers
```powershell
Invoke-Command -ComputerName (Get-Content $fileName) -ScriptBlock $commands
```
## From CSV File
```powershell
Invoke-Command -ComputerName (Import-Csv $fileName.csv | Select-ExpandProperty "Computer Name") -ScriptBlock $commands
```
## Dynamic List from AD
```powershell
Invoke-Command -ComputerName (Get-ADComputer –Filter * | Select –ExpandProperty Name) -ScriptBlock $commands
```
# Using Credentials
```powershell
Invoke-Command -ScriptBlock { Param($c) $commands -Credential $c} -ComputerName $computerName -ArgumentList (Get-Credential)
```
## Start a Command and Retrieve Results Later
### Execute Command
```powershell
Invoke-Command -ComputerName $computerName -InDisconnectedSession -ScriptBlock { $command }
```
### Retrieve Results
```powershell
Receive-PSSession -ComputerName $computerName -Name $sessionName
```
## Pass Variables
```powershell
$ps = "Windows PowerShell"
Invoke-Command -ComputerName $computerName -ScriptBlock { 
$command(Get-WinEvent) -LogName $Using:ps } 
```

```powershell
$s = New-PSSession -ComputerName $computerName
$ps = "Windows PowerShell"
Invoke-Command -Sessions $s -ScriptBlock { 
$command(Get-WinEvent) -LogName $Using:ps}
```

```powershell
$Log = 'Security'
$Quantity = 10
Invoke-Command -ComputerName $computerName -ScriptBlock { Param($x,$y) $command(Get-WinEvent) -LogName $x -MaxEvents $y } -ArgumentList $Log,$Quantity
```
---
# PSSession
## Create Session
```powershell
New-PSSession -ComputerName $computerName -Credential $username
```
### On Multiple Computers
```powershell
New-PSSession -ComputerName $computerName,$computerName
```
## Connect to Session
```powershell
Enter-PSSession -ComputerName $computerName -Credential $username
```
## Close Session
```powershell
Exit-PSSession
```
## Import Commands
```powershell
$s = New-PSSession -ComputerName $computerName 
Import-PSSession -Session $s -Module $moduleName
```
## Pass Variables
```powershell
$moduleName = NetAdapter
$s = New-PSSession -ComputerName $computerName 
Enter-PSSession -Session $s -Credential $username
# From other Computer
Import-Module $Using:moduleName
```