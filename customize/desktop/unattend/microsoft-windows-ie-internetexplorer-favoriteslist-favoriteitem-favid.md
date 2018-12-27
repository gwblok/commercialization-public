---
title: FavID
description: FavID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fcfddfa3-aa8c-47b1-93bc-86ea22b61cf7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavID


`FavID` specifies a unique key to associate with a [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique string value (key) to represent the <code>FavoriteItem</code> in the unattended installation answer file. <code>FavID </code>must be unique for each <a href="microsoft-windows-ie-internetexplorer-favoriteslist.md" data-raw-source="[FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md)">FavoritesList</a>. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) | **FavID**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies how to configure favorites.

```
<FavoritesList>
   <FavoriteItem wcm:action="add">
      <FavIconFile>C:\Windows\favlink1.ico</FavIconFile>
      <FavID>Favorite1</FavID>
      <FavOffLine>true</FavOffLine>
      <FavTitle>My Favorite</FavTitle>
      <FavURL>http://www.fabrikam.com/myfav1</FavURL>
   </FavoriteItem>
  <FavoriteItem wcm:action="add">
      <FavIconFile> C:\Windows\favlink2.ico </FavIconFile>
      <FavID>Favorite2</FavID>
      <FavOffLine>true</FavOffLine>
      <FavTitle>Favorite 2</FavTitle>
      <FavURL>http://www.fabrikam.com/myfav2</FavURL>
   </FavoriteItem>
</FavoritesList>
```

## Related topics


[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)

 

 







