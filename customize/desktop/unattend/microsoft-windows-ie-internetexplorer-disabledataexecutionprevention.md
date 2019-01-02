---
title: DisableDataExecutionPrevention
description: DisableDataExecutionPrevention
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6c24c327-43ab-42d8-a4c1-f4bc02cd53ad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableDataExecutionPrevention


`DisableDataExecutionPrevention` specifies whether Internet Explorer prevents arbitrary code execution from a virtual-memory page that is marked as non-executable.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Internet Explorer prevents arbitrary code execution from virtual memory pages that are marked as non-executable.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Internet Explorer allows arbitrary code execution from virtual memory pages that are marked as non-executable.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **DisableDataExecutionPrevention**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure Internet Explorer to allow arbitrary code execution from virtual memory pages marked as non-executable.

```
<DisableDataExecutionPrevention>false</DisableDataExecutionPrevention>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







