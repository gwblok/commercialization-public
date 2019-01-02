---
title: FavoritesOnTop
description: FavoritesOnTop
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6642f537-802e-4c31-96c4-67988a5a787d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavoritesOnTop


`FavoritesOnTop` specifies whether to add new favorites to the top of the **Favorites** menu.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Adds new favorites to the top of the <strong>Favorites</strong> menu.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Adds new favorites to the bottom of the <strong>Favorites</strong> menu. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **FavoritesOnTop**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies that new favorites are added to the top of the **Favorites** menu.

```
<FavoritesOnTop>true</FavoritesOnTop>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







