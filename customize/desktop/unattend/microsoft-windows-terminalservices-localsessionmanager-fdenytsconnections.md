---
title: fDenyTSConnections
description: fDenyTSConnections
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ca7b2f3e-d1a2-4077-a9e9-8d6c2e7233c1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# fDenyTSConnections


`fDenyTSConnections` specifies whether Remote Desktop connections are enabled.

There are several settings that must be configured to enable Remote Desktop connections during an unattended installation. First, you must enable Remote Desktop connections by using the `fDenyTSConnections` setting. You must also enable the Remote Desktop group in Windows Firewall. For more information, see "Enable Remote Desktop" in the Windows Assessment and Deployment Kit (Windows ADK).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that remote desktop connections are denied. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that remote desktop connections are enabled.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-LocalSessionManager]microsoft-windows-terminalservices-localsessionmanager.md) | **fDenyTSConnections**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-LocalSessionManager](microsoft-windows-terminalservices-localsessionmanager.md).

## XML Example


The following XML output shows how to set this element so that remote terminal service connections are enabled.

```
<fDenyTSConnections>false</fDenyTSConnections>
```

## Related topics


[Microsoft-Windows-TerminalServices-LocalSessionManager](microsoft-windows-terminalservices-localsessionmanager.md)

 

 







