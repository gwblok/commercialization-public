---
title: FavoriteItem
description: FavoriteItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b6c2ba28-2bd6-4ab0-9f16-68d025631ed5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FavoriteItem

`FavoriteItem` specifies the settings for the icon that appears to the user, which sites must appear offline, the name that appears in the Favorites folder, and the associated Uniform Resource Locator (URL).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FavIconFile](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem-faviconfile.md) | Specifies the icon to associate with the <code>FavoriteItem</code> in the Favorites folder. |
| [FavID](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem-favid.md) | Specifies a unique key to associate with a <code>FavoriteItem</code>. |
| [FavOffLine](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem-favoffline.md) | Specifies whether to make the <code>FavoriteItem</code> available for offline browsing. |
| [FavTitle](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem-favtitle.md) | Specifies a friendly name for the site appearing as a <code>FavoriteItem</code> in the Favorites folder. |
| [FavURL](microsoft-windows-ie-internetexplorer-favoriteslist-favoriteitem-favurl.md) | Specifies a fully qualified path to the URL of each <code>FavoriteItem</code>. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md) | **FavoriteItem**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output specifies how to configure favorites.

```XML
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

[FavoritesList](microsoft-windows-ie-internetexplorer-favoriteslist.md)
