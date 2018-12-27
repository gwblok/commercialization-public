---
title: fAllowToGetHelp
description: fAllowToGetHelp
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 90f30e44-36ee-40aa-9c30-88d5a70360f5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# fAllowToGetHelp


`fAllowToGetHelp` specifies that the user can request assistance from a friend or a support professional.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the user can request assistance from a friend or a support professional.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the user cannot request assistance from a friend or a support professional. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md) | **fAllowToGetHelp**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md).

## XML Example


The following XML output shows how to enable a friend or a support professional to offer help. The ticket is configured to expire after one day.

```
<CreateEncryptedOnlyTickets>true</CreateEncryptedOnlyTickets>
<fAllowToGetHelp>true</fAllowToGetHelp>
<fAllowFullControl>true</fAllowFullControl>
<MaxTicketExpiry>1</MaxTicketExpiry>
<MaxTicketExpiryUnits>2</MaxTicketExpiryUnits>
```

## Related topics


[Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md)

 

 







