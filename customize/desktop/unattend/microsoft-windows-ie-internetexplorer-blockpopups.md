---
title: BlockPopups
description: BlockPopups
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 03f138ae-4496-4200-8e3b-d62e59c6e7dc
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BlockPopups


`BlockPopups` specifies whether to block pop-up windows for the user.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>yes</strong></p></td>
<td><p>Specifies that pop-up windows are blocked. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>no</strong></p></td>
<td><p>Specifies that pop-up windows are not blocked.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **BlockPopups**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies how to disable pop-up blocking.

```
<BlockPopups>no</BlockPopups>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







