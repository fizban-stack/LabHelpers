# Enumerate Services Running as a List of Users
```powershell
$names = @('Route Match','Sage 100','Sage Support','Sophos Update','Time Trax')
Get-CimInstance Win32_Service | Where-Object { $_.StartName -in $names } | Select-Object Name, StartName, State | Sort-Object StartName
```
