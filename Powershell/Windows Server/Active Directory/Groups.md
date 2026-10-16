# New Group
```powershell
New-ADGroup -Name $groupName -GroupScope $scope
```
## Common Parameters
| Parameter       | Description                                                                                                                   |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| ‑Name           | Defines the name of a group                                                                                                   |
| ‑GroupScope     | Defines the scope of a group as **DomainLocal**, **Global**, or **Universal**; you must provide this parameter                |
| ‑DisplayName    | Defines the Lightweight Directory Access Protocol (LDAP) display name for an object                                           |
| ‑GroupCategory  | Defines whether a group is a security group or a distribution group; if you don't specify either, a security group is created |
| ‑ManagedBy      | Defines a user or group that can manage a group                                                                               |
| ‑Path           | Defines the OU or container in which a group is created                                                                       |
| ‑SamAccountName | Defines a name that is backward-compatible with older operating systems                                                       |
# Modify Group Properties
```powershell
Set-ADGroup
```
# Display Group Properties
```powershell
Get-ADGroup
```
# Delete Group
```powershell
Remove-ADGroup
```
# Modify Group
***Takes Group Name or List of Groups as Parameter***
## Add Members to Group
```powershell
Add-ADGroupMember
```
## Display Group Members
```powershell
Get-ADGroupMember
```
## Remove Members from Group
```powershell
Remove-ADGroupMember
```
# Modify Object Membership
***Takes Object Name (User or Computer) or List of Objects as Parameter***
## Add Object to Group
```powershell
Add-ADPrincipalGroupMembership
```
## Display Object Group Membership
```powershell
Get-ADPrincipalGroupMembership
```
## Remove Object from Group
```powershell
Remove-ADPrincipalGroupMembership
```