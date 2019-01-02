---
title: FavTitle
description: FavTitle
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 83975cef-050d-48fb-b811-8e1ae0f84cd9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FavTitle


`FavTitle` specifies the friendly name of [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) that appears in the Favorites folder.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name_of_link</em></p></td>
<td><p>Specifies the name of your <a href="microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md" data-raw-source="[FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md)">FavoriteItem</a>, based on your license terms, for inclusion within the Favorites folder.</p>
<p>You can organize favorite items into folders by preceding the value of <code>FavTitle</code> with a folder name. For example, the value <strong>Fabrikam Links\Fabrikam Support</strong> creates the Fabrikam Support <code>FavoriteItem</code> in a Fabrikam Links folder.</p>
<p><code>FavTitle</code> must appear only once for each <code>FavoriteItem</code>.</p>
<p><em>Name_of_link</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | [FavoriteItem](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem.md) | **FavTitle**

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

 

 







