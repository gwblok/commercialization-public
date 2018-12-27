---
title: UserAuthentication
description: UserAuthentication
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 72eb3142-fc7b-49c4-afe5-218589e4a0c1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UserAuthentication


`UserAuthentication` specifies how users are authenticated before the remote desktop connection is established.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that Network-Level user authentication is not required before the remote desktop connection is established. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that Network-Level user authentication is required.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md) | **UserAuthentication**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md).

## XML Example


The following XML output shows how to set the Microsoft-Windows-TerminalServices-RDP-WinStationExtensions component.

```
<SecurityLayer>2</SecurityLayer>
<UserAuthentication>0</UserAuthentication>
```

## Related topics


[Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md)

 

 







