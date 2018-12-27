---
title: FavURL
description: FavURL
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7b9cea4b-a6ef-40cd-906a-32062e5951fd
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavURL


`FavURL` specifies a Uniform Resource Locator (URL) to associate with a [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Url</em></p></td>
<td><p>Specifies the fully qualified path that begins with the <strong>http://</strong> prefix to the URL of each <a href="microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md" data-raw-source="[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)">FavoriteItem</a>. <em>Url</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) | **FavURL**

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

 

 







