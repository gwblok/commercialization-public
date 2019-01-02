---
title: CacheLimit
description: CacheLimit
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 715cebfd-5a1e-40ac-81e0-2c05e4d0fd56
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CacheLimit


`CacheLimit` specifies the amount of disk space to use for storing temporary Internet files.

**Note**  
We recommend setting this value to at least 51200 (50 MB), because lower values may negatively affect browsing performance. For computers with limited drive space, lower values may be used.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Size_in_kilobytes</em></p></td>
<td><p>Specifies the amount of disk space to use for storing temporary Internet files.</p>
<p><em>Size_in_kilobytes</em> is an integer. The allowed values are from 8192 (= 8 MB) to 1048576 (= 1 GB). If <em>Size_in_kilobytes</em> is set to a value smaller than 8192, then 8192 will be used.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **CacheLimit**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to reserve 100 MB of disk space for storing temporary Internet files.

```
<CacheLimit>102400</CacheLimit>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







