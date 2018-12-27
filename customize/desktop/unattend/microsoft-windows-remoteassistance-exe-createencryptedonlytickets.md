---
title: CreateEncryptedOnlyTickets
description: CreateEncryptedOnlyTickets
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 325d450d-c35f-45f7-9950-404676a3ede5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CreateEncryptedOnlyTickets


`CreateEncryptedOnlyTickets` specifies whether only encrypted tickets can be created for remote assistance.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that tickets must be encrypted. /p&gt;</td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that tickets do not need to be encrypted. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md) | **CreateEncryptedOnlyTickets**

## Valid Configuration Passes


specialize

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md).

## XML Example


The following XML output shows how to allow a friend or support professional to offer help by using an encrypted ticket. The ticket is configured to expire after one day.

```
<CreateEncryptedOnlyTickets>true</CreateEncryptedOnlyTickets>
<fAllowToGetHelp>true</fAllowToGetHelp>
<fAllowFullControl>true</fAllowFullControl>
<MaxTicketExpiry>1</MaxTicketExpiry>
<MaxTicketExpiryUnits>2</MaxTicketExpiryUnits>
```

## Related topics


[Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md)

 

 







