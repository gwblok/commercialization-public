---
title: IntranetCompatibilityMode
description: IntranetCompatibilityMode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fe4e8e39-4761-4867-bff9-7c2b11ff62e2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IntranetCompatibilityMode


`IntranetCompatibilityMode` specifies whether intranet sites render using Compatibility view.

In Compatibility view, Internet Explorer displays Web pages as they would be shown on an earlier version of Internet Explorer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Internet Explorer will render in Compatibility mode for intranet sites.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Internet Explorer will not render in Compatibility mode for intranet sites.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | `IntranetCompatibilityMode`

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to render intranet sites using Compatibility mode.

```
<IntranetCompatibilityMode>true</IntranetCompatibilityMode>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







