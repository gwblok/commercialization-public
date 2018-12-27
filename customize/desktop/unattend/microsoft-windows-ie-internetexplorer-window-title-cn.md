---
title: Window\_Title\_CN
description: Window\_Title\_CN
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dc1e6ff4-6aef-4013-8835-1e9b63c904c5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Window\_Title\_CN


`Window_Title_CN` specifies the company name appended to the window title text.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name_of_company</em></p></td>
<td><p>Specifies the company name to be appended to the window title, including the text &quot;Internet Explorer provided by&quot; or its localized equivalent. <em>Name_of_company</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **Window\_Title\_CN**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies the text appended to the window title.

```
<Window_Title_CN>Fabrikam</Window_Title_CN>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







