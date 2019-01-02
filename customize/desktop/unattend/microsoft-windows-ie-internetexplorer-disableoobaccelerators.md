---
title: DisableOOBAccelerators
description: DisableOOBAccelerators
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4323ae7e-5690-4feb-b0c2-73a53f4adb30
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableOOBAccelerators


`DisableOOBAccelerators` specifies whether the default Internet Explorer Accelerators are available.

Accelerators are menu options in Internet Explorer that help automate common browser-related tasks. In Internet Explorer, when you right-click selected text, Accelerators appear in the list of available options. For example, if you select an address, you can use an Accelerator to show a map of that address.

Examples of the default Internet Explorer Accelerators include: **Blog with Windows Live**, **Define with Encarta**, **E-mail with Windows Live**, and **Map with Live Search**.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>The default Accelerators are not included in Internet Explorer.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>The default Accelerators are included in Internet Explorer.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **DisableOOBAccelerators**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML example demonstrates not including the default Internet Explorer Accelerators.

```
<DisableOOBAccelerators>true</DisableOOBAccelerators>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md)

[DisableAccelerators](microsoft-windows-ie-internetexplorer-disableaccelerators.md)

 

 







