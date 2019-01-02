---
title: DisableAutoDaylightTimeSet
description: DisableAutoDaylightTimeSet
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: df38c80c-5b1f-4b01-bd24-b18690483299
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableAutoDaylightTimeSet


`DisableAutoDaylightTimeSet` specifies whether to enable the destination computer to automatically change between daylight saving time and standard time.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the time on the computer uses standard time.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the time on the computer switches between standard time and daylight saving time. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **DisableAutoDaylightTimeSet**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to disable daylight saving time.

```
<DisableAutoDaylightTimeSet>true</DisableAutoDaylightTimeSet>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

 

 







