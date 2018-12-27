---
title: AddonGuid
description: AddonGuid
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e28f7125-8f45-4c5b-a5b3-5287c187d2e6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AddonGuid


`AddonGuid` specifies a GUID for an Internet Explorer Browser Extension.

Browser Extensions are plug-in modules used to add functionality to Internet Explorer. Examples of Browser Extensions include shortcut menu extensions, toolbars, explorer bars, and Browser Help Objects.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>{<code>GUID</code>}</p></td>
<td><p>Specifies a GUID for a Browser Extension.</p>
<p><code>GUID</code> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [InstalledBrowserExtensions](microsoft-windows-ie-internetexplorer-installedbrowserextensions.md) | [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbrowserextensions-addonguiditem.md) | **AddonGuid**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to set two Internet Explorer Browser Extensions.

```
<InstalledBrowserExtensions>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</InstalledBrowserExtensions>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







