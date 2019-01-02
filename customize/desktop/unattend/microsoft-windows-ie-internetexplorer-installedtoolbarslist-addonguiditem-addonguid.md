---
title: AddonGuid
description: AddonGuid
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2d38559b-24e8-41f5-82f6-bad83216d36a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AddonGuid


`AddonGuid` specifies a GUID for an Internet Explorer toolbar.

Toolbars are plug-in modules used to add functionality to Internet Explorer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>{<code>GUID</code>}</p></td>
<td><p>Specifies a GUID for a toolbar.</p>
<p><code>GUID</code> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [InstalledToolbarsList](microsoft-windows-ie-internetexplorer-installedtoolbarslist.md) | [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedtoolbarslist-addonguiditem.md) | **AddonGuid**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to specify a GUID for Internet Explorer toolbars.

```
<InstalledToolbarsList>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</InstalledToolbarsList>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







