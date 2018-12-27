---
title: FavOffLine
description: FavOffLine
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 657f6b95-06b7-4a84-ad4f-703c61fb1593
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavOffLine


`FavOffLine` specifies whether to make the [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) available for offline browsing.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the <a href="microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md" data-raw-source="[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)">FavoriteItem</a> is available for offline browsing.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the <a href="microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md" data-raw-source="[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)">FavoriteItem</a> is not available for offline browsing. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) | **FavOffLine**

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

 

 







