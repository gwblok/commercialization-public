---
title: FavoriteBarItem
description: FavoriteBarItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 908e2220-d6dd-4c8c-9911-54c9ff39d124
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FavoriteBarItem

`FavoriteBarItem` contains the settings used to add predefined Favorite items to the Favorite bar.

A Favorite can include web content such as links, feeds, web slices, or documents, such as Microsoft Word, Microsoft Excel and Microsoft PowerPoint documents.

To add a predefined Favorite bar item in Windows System Image Manager, add the **FavoriteBarItems** component to your answer file. Next, right-click **FavoriteBarItems**, and select **Insert New FavoriteBarItem**.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ItemKey](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem-itemkey.md) | Specifies a unique key for the Favorite bar item. |
| [ItemName](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem-itemname.md) | Specifies the name that appears in the Favorite bar. |
| [ItemType](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem-itemtype.md) | Specifies the type of Favorite. |
| [ItemUrl](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem-itemurl.md) | Specifies the path to the Favorite. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoriteBarItems](microsoft-windows-ie-internetexplorer-favoritebaritems.md)| **FavoriteBarItem**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML example shows three Favorite bar items.

```XML
<FavoriteBarItems>
  <FavoriteBarItem>
    <ItemKey>1</ItemKey>
    <ItemName>Name1</ItemName>
    <ItemUrl>http://www.fabrikam.com/stockwatch#stockprice</ItemUrl>
    <ItemType>Webslice</ItemType>
  </FavoriteBarItem>
  <FavoriteBarItem>
    <ItemKey>2</ItemKey>
    <ItemName>Name2</ItemName>
    <ItemUrl>http://www.msn.com/rss/ie8_slideshow.aspx</ItemUrl>
    <ItemType>Webslice</ItemType>
  </FavoriteBarItem>
  <FavoriteBarItem>
    <ItemKey>3</ItemKey>
    <ItemName>Name3</ItemName>
    <ItemUrl>http://www.fabrikam.com/xml/HomePage.xml</ItemUrl>
    <ItemType>Headline</ItemType>
  </FavoriteBarItem>
</FavoriteBarItems>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)
