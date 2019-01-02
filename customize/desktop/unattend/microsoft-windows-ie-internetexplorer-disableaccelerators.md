---
title: DisableAccelerators
description: DisableAccelerators
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e3c7680e-24b3-4aa4-a3f9-45c266fde0db
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableAccelerators


`DisableAccelerators` specifies whether Accelerators are available in Internet Explorer.

Accelerators are menu options in Internet Explorer that help automate common browser-related tasks. In Internet Explorer, when you right-click selected text, Accelerators appear in the list of available options. For example, if you select an address, you can use an Accelerator to show a map of that address.

When `DisableAccelerators` is set to **false**, Accelerators set through [Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md) are also disabled.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the <strong>Accelerators</strong> menu does not appear in Internet Explorer.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the <strong>Accelerators</strong> menu appears in Internet Explorer.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **DisableAccelerators**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to disable the **Accelerators** menu.

```
<DisableAccelerators>true</DisableAccelerators>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md)

[DisableOOBAccelerators](microsoft-windows-ie-internetexplorer-disableoobaccelerators.md)

 

 







