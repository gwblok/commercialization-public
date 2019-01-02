---
title: Bridge
description: Bridge
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2edee894-f32f-45db-b058-449cddca9cdd
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Bridge


`Bridge` specifies the adapters to bridge together to form a home network. This entry requires at least two adapters.

**Note**  
Not all adapters can be bridged.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Bridge</em></p></td>
<td><p>Specifies the adapters. <em>Bridge</em> is a comma-delimited list.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-NetworkBridge](microsoft-windows-networkbridge.md) | **Bridge**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkBridge](microsoft-windows-networkbridge.md).

## XML Example


The following XML output shows how to set the bridge.

```
<Bridge>{A123B456-C789-DE00-FFA4-E73F7B925305},{123F654D-00FF-AABB-CCDD1-EEFF7777702}</Bridge>
```

## Related topics


[Microsoft-Windows-NetworkBridge](microsoft-windows-networkbridge.md)

[Microsoft-Windows-SharedAccess]microsoft-windows-sharedaccess.md)

 

 







