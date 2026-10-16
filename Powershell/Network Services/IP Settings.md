# IP Address
## New Static IP Address
```powershell
New-NetIPAddress -IPAddress 192.168.1.10 -InterfaceAlias "Ethernet" -PrefixLength 24 -DefaultGateway 192.168.1.1
```
### Common Parameters
|Parameter|Description|
|---|---|
|`-IPAddress`|Defines the IPv4 or IPv6 address to create|
|`-InterfaceIndex`|Defines the network interface, by index, for the IP address|
|`-InterfaceAlias`|Defines the network interface, by name, for the IP address|
|`-DefaultGateway`|Defines the IPv4 or IPv6 address of the default gateway host|
|`-PrefixLength`|Defines the subnet mask for the IP address|
## Display IP Address Properties
```powershell
Get-NetIPAddress
```
## Modify IP Address Properties
```powershell
Set-NetIPAddress
```
## Delete IP Address
```powershell
Remove-NetIPAddress
```
---
# IP Routing
## New Routing Table Entry
```powershell
New-NetRoute -DestinationPrefix "0.0.0.0/0" -InterfaceAlias "Ethernet" -NextHop 192.168.1.1
```
### Common Parameters
|Parameter|Description|
|---|---|
|‑DestinationPrefix|Defines the destination prefix of an IP route|
|‑InterfaceAlias|Defines the network interface, by alias, for an IP route|
|‑InterfaceIndex|Defines the network interface, by index, for an IP route|
|‑NextHop|Defines the next hop for an IP route|
|‑RouteMetric|Defines the route metric for an IP route|
## Display Route Properties
```powershell
Get-NetRoute
```
# Modify Route Properties
```powershell
Set-NetRoute
```
## Remove Routing Table Entry
```powershell
Remove-NetRoute
```