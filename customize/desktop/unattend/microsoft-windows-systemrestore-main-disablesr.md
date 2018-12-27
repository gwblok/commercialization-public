---
title: DisableSR
description: DisableSR
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c1eecbf9-dd5f-41f6-96c1-d77e791a5f5b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableSR


`DisableSR` enables or disables System Restore.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Enables System Restore and creates restore points according to events and a schedule. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that no more restore points will be created. This limits the ongoing usefulness of System Restore on the computer.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-SystemRestore-Main](microsoft-windows-systemrestore-main.md) | **DisableSR**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SystemRestore-Main](microsoft-windows-systemrestore-main.md).

## XML Example


The following XML output shows how to disable System Restore.

```
<DisableSR>1</DisableSR>
```

## Related topics


[Microsoft-Windows-SystemRestore-Main](microsoft-windows-systemrestore-main.md)

 

 







