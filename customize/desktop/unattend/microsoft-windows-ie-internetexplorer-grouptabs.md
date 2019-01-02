---
title: GroupTabs
description: GroupTabs
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ecb4e010-5f69-47a5-976e-22b584c7ea92
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# GroupTabs


`GroupTabs` specifies whether Internet Explorer displays tabs in groups.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Internet Explorer displays the tabs in groups.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Internet Explorer does not display tabs in groups.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **GroupTabs**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure Internet Explorer not to display tabs in groups.

```
<GroupTabs>false</GroupTabs>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







