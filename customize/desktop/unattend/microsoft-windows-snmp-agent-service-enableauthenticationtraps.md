---
title: EnableAuthenticationTraps
description: EnableAuthenticationTraps
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 11d8b8b5-cbb7-40e9-9f03-52dde6442a41
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableAuthenticationTraps


`EnableAuthenticationTraps` specifies whether to send an authentication trap when an unauthorized community or host requests information.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Sends an authentication trap when an unauthorized community or host requests information. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not send an authentication trap when an unauthorized community or host requests information.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | **EnableAuthenticationTraps**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md).

## XML Example


The following XML output shows how to disable authentication traps.

```
<EnableAuthenticationTraps>false</EnableAuthenticationTraps>
```

## Related topics


[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md)

 

 







