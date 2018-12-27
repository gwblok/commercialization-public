---
title: Home\_Page
description: Home\_Page
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7bdf9947-091b-4c72-8c82-b4e2a70a9d04
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Home\_Page


`Home_Page` specifies the Uniform Resource Locator (URL) for the default home page that appears when the user starts Internet Explorer. To set additional home pages, use the Microsoft-Windows-IE-InternetExplorer/[StartPages](microsoft-windows-ie-internetexplorer-startpages.md) setting.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Url</em></p></td>
<td><p>Describes the fully qualified URL path. <em>Url</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **Home\_Page**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies the fully qualified URL.

```
<Home_Page>http://www.fabrikam.com</Home_Page>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[StartPages](microsoft-windows-ie-internetexplorer-startpages.md)

 

 







