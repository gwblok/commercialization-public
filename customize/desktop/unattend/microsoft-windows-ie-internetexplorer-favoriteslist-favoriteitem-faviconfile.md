---
title: FavIconFile
description: FavIconFile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 14897601-aebc-483f-9966-12066730acd5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavIconFile


`FavIconFile` specifies the icon to associate with the [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) in the Favorites folder.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_and_file_name</em></p></td>
<td><p>Specifies the location and the name of the icon to associate with the <a href="microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md" data-raw-source="[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)">FavoriteItem</a> in the Favorites folder, for example, C:\Windows\favlink2.ico. <em>Path_and_file_name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) | **FavIconFile**

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
      <FavIconFile>C:\Windows\favlink2.ico</FavIconFile>
      <FavID>Favorite2</FavID>
      <FavOffLine>true</FavOffLine>
      <FavTitle>Favorite 2</FavTitle>
      <FavURL>http://www.fabrikam.com/myfav2</FavURL>
   </FavoriteItem>
</FavoritesList>
```

## Related topics


[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)

 

 







