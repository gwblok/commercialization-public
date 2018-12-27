---
title: MaxTicketExpiry
description: MaxTicketExpiry
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7ef10280-6dce-4c7b-96c1-96161e75f202
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MaxTicketExpiry


`MaxTicketExpiry` specifies the maximum length of a ticket in the units set by the [MaxTicketExpiryUnits](microsoft-windows-remoteassistance-exe-maxticketexpiryunits.md) setting. The value of the MaxTicketExpiryUnits setting can be set to minutes, hours, or days. By default, a ticket expires in six (6) hours.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>MaxTicketExpiry_value</em></p></td>
<td><p>Specifies the number of expiration units before a ticket times out. The default value is <strong>6</strong>.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-RemoteAssistance-Exe](microsoft-windows-remoteassistance-exe.md) | **MaxTicketExpiry**

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

 

 







