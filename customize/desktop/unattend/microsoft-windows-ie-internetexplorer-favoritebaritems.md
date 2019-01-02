---
title: FavoriteBarItems
description: FavoriteBarItems
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c19b1d73-6948-455d-816c-b74b69d65d0b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FavoriteBarItems

`FavoriteBarItems` contains the settings used to add predefined Favorite items to the Favorite bar.

A Favorite can include web content such as links, feeds, web slices, or documents, such as Microsoft Word, Microsoft Excel and Microsoft PowerPoint documents.

To add a predefined Favorite bar item in Windows System Image Manager, add the **FavoriteBarItems** component to your answer file. Next, right-click **FavoriteBarItems**, and select **Insert New FavoriteBarItem**.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FavoriteBarItem](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem.md) | Specifies settings for each Favorite bar item. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **FavoriteBarItems**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

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
