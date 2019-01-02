---
title: AddonGuid
description: AddonGuid
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9e5da1c3-b28d-4968-a149-61ff6304875d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AddonGuid


`AddonGuid` specifies a GUID for an Internet Explorer Browser Help Object.

Browser Help Objects are add-on modules used to add functionality to Internet Explorer. Examples of Browser Help Objects include toolbars, animated mouse pointers, and stock tickers.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>{<code>GUID</code>}</p></td>
<td><p>Specifies a GUID for a Browser Help Object.</p>
<p><code>GUID</code> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [InstalledBHOList](microsoft-windows-ie-internetexplorer-installedbholist.md) | [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbholist-addonguiditem.md) | **AddonGuid**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to specify a GUID for two Internet Explorer Browser Help Objects.

```
<InstalledBHOList>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123-d1e1f4a-5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1-e1f4a5a-6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</InstalledBHOList>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







