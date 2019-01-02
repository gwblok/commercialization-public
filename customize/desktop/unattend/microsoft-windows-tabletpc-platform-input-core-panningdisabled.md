---
title: PanningDisabled
description: PanningDisabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e47c92bc-2d57-48fc-b68c-fdcb206e7d08
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PanningDisabled


`PanningDisabled` specifies whether panning is disabled on a Tablet PC. When panning is enabled users can scroll through a page by touching the screen and sliding their finger up or down.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Disables panning.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Enables panning. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md) | **PanningDisabled**

## Valid Configuration Passes


offlineServicing

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example


The following XML output shows how to disable panning on a Tablet PC.

```
<PanningDisabled>true</PanningDisabled>
```

## Related topics


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)

 

 







