---
title: TabProcessGrowth
description: TabProcessGrowth
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c80d9bdb-a943-407e-9f39-e742c7091377
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TabProcessGrowth


`TabProcessGrowth` sets the rate at which Internet Explorer creates new tab processes.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>High</p></td>
<td><p>Internet Explorer allows the tab process to grow very quickly, and is intended only for computers with ample physical memory.</p></td>
</tr>
<tr class="even">
<td><p>Medium</p></td>
<td><p>Internet Explorer allows a medium number of tab processes to start.</p>
<p>This is the default setting.</p></td>
</tr>
<tr class="odd">
<td><p>Low</p></td>
<td><p>Internet Explorer creates very few tab processes.</p></td>
</tr>
</tbody>
</table>

 

If no value is entered, then the default setting is to create the optimal number of tab processes based on the operating system and amount of physical memory. We recommend the default setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **TabProcessGrowth**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure Internet Explorer to allow tab processes to grow quickly.

```
<TabProcessGrowth>Large</TabProcessGrowth>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







