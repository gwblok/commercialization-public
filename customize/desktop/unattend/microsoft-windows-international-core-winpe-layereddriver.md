---
title: LayeredDriver
description: LayeredDriver
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bb468c34-f1d0-4035-bc76-3f8fbe78cd93
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LayeredDriver


`LayeredDriver` specifies a keyboard driver to use for Japanese or Korean keyboards.

In Japan, many retail users have 106-key keyboards, while some others have 101- or 102-key keyboards. In Korea, several different types of keyboards are available, some with different numbers of keys.

This setting provides a means to select the specific keyboard to configure during Windows Setup.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Specifies the PC/AT Enhanced keyboard (101/102-key).</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Specifies the Korean PC/AT 101-Key Compatible keyboard or the Microsoft Natural keyboard (type 1).</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Specifies the Korean PC/AT 101-Key Compatible keyboard or the Microsoft Natural keyboard (type 2).</p></td>
</tr>
<tr class="even">
<td><p><strong>4</strong></p></td>
<td><p>Specifies the Korean PC/AT 101-Key Compatible keyboard or the Microsoft Natural keyboard (type 3).</p></td>
</tr>
<tr class="odd">
<td><p><strong>5</strong></p></td>
<td><p>Specifies the Korean keyboard (103/106-key).</p></td>
</tr>
<tr class="even">
<td><p><strong>6</strong></p></td>
<td><p>Specifies the Japanese keyboard (106/109-key).</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | **LayeredDriver**

## Valid Configuration Passes


windowsPE

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example configures the `LayeredDriver` setting to use the Japanese (106/109) keyboard.

```
<LayeredDriver>6</LayeredDriver>
```

## Related topics


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







