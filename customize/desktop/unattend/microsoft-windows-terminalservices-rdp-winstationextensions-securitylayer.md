---
title: SecurityLayer
description: SecurityLayer
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1d4418ed-b7a7-4017-8d89-61270b6e47c9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SecurityLayer


`SecurityLayer` specifies how servers and clients authenticate each other before a remote desktop connection is established.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that the Microsoft Remote Desktop Protocol (RDP) is used by the server and the client for authentication before a remote desktop connection is established. RDP is a Microsoft protocol that supports terminal services across heterogeneous network environments.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that the server and the client negotiate the method for authentication before a remote desktop connection is established. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>2</strong></p></td>
<td><p>Specifies that the Transport Layer Security (TLS) protocol is used by the server and the client for authentication before a remote desktop connection is established.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md) | **SecurityLayer**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md).

## XML Example


The following XML output shows how to set the Microsoft-Windows-TerminalServices-RDP-WinStationExtensions component.

```
<SecurityLayer>2</SecurityLayer>
<UserAuthentication>2</UserAuthentication>
```

## Related topics


[Microsoft-Windows-TerminalServices-RDP-WinStationExtensions](microsoft-windows-terminalservices-rdp-winstationextensions.md)

 

 







