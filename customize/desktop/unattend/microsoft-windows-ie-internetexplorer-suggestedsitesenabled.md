---
title: SuggestedSitesEnabled
description: SuggestedSitesEnabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8c81e8e9-6b57-4b38-8fc7-78f70779c5be
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SuggestedSitesEnabled


`SuggestedSitesEnabled` specifies whether the **Suggested Sites** Web Slice appears in Internet Explorer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Internet Explorer displays the <strong>Suggested Sites</strong> Web Slice.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Internet Explorer does not display the <strong>Suggested Sites</strong> Web Slice.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **SuggestedSitesEnabled**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure Internet Explorer to hide the **Suggested Sites** Web Slice.

```
<SuggestedSitesEnabled>false</SuggestedSitesEnabled>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







