---
title: MSCompatibilityMode
description: MSCompatibilityMode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d3697212-7b62-46ce-9b46-8dc7ea3f86e4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MSCompatibilityMode


`MSCompatibilityMode` specifies whether Compatibility View uses updated website lists from Microsoft.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Compatibility View uses updated website lists from Microsoft to determine how to display a website.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Compatibility View does not use website lists from Microsoft.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **MSCompatibilityMode**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to specify that Compatibility View uses updated website lists from Microsoft to determine how to display a website.

```
<MSCompatibilityMode>true</MSCompatibilityMode>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







