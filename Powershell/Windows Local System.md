| **Cmdlet**         | **Description**                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Get-ComputerInfo` | Retrieves all system and operating system properties from the computer                                                                           |
| `Get-Service`      | Retrieves a list of all services on the computer                                                                                                 |
| `Get-EventLog`     | Retrieves events and event logs from local and remote computers (only available in Windows PowerShell 5.1)                                       |
| `Get-Process`      | Retrieves a list of all active processes on a local or remote computer                                                                           |
| `Stop-Service`     | Stops one or more running services                                                                                                               |
| `Stop-Process`     | Stops one or more running processes                                                                                                              |
| `Stop-Computer`    | Shuts down local and remote computers                                                                                                            |
| `Clear-EventLog`   | Deletes all of the entries from the specified event logs on the local computer or on remote computers (only available in Windows PowerShell 5.1) |
| `Clear-RecycleBin` | Deletes the content of a computer's recycle bin                                                                                                  |
| `Restart-Computer` | Restarts the operating system on local and remote computers                                                                                      |
| `Restart-Service`  | Stops and then starts one or more services                                                                                                       |
## Permissions
|**Cmdlet**|**Description**|
|---|---|
|**Get-Acl**|This cmdlet gets objects that represent the security descriptor of a file or resource. The security descriptor includes the access control lists (ACLs) of the resource. The ACL lists permissions that users and groups have to access the resource.|
|**Set-Acl**|This cmdlet changes the security descriptor of a specified item, such as a file, folder, or a registry key, to match the values in a security descriptor that you supply.|
### Get-ACL
By default, the output displays in a table format. If you pipe the output to a list format, you can review all the information included in the security descriptor.

```powershell
Get-Acl -Path C:\Folder1|Format-List

```

By using the following command, you can retrieve a more verbose list of the access property with the file system rights, access control type, and inheritance settings for the specified object:

```powershell
(Get-Acl -Path C:\Folder1).Access

```

You can also retrieve only specific Access properties formatted in a table format, as the following example depicts:

```powershell
(Get-Acl -Path C:\Folder1).Access|Format-Table IdentityReference, FileSystemRights, AccessControlType, IsInherited
```

### Set-Acl

The following example assigns the **Modify** permission to **C:\Folder1** for a local user named **User1**. The first step is to declare a variable that includes the existing ACL rules for **Folder1**.

```powershell
$ACL = Get-Acl -Path C:\Folder1

```

The second step is to create a new FileSystemAccessRule variable which specifies the access specifications to be applied:

```powershell
$AccessRule = New-Object System.Security.AccessControl.FileSystemAccessRule("User1","Modify","Allow")

```

The third step is to add the new access rule to the existing ACL rules for **Folder1**:

```powershell
$ACL.SetAccessRule($AccessRule)

```

Finally, you need to apply the new ACL to **Folder1**:

```powershell
$ACL | Set-Acl -Path C:\Folder1
```
#### Copy an ACL
```powershell
Get-Acl -Path C:\Folder1|Set-Acl -Path C:\Folder2
```