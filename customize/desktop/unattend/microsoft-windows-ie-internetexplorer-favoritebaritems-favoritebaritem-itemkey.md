---
title: ItemKey
description: ItemKey
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d7115f87-2872-4288-ac42-9bc0887c31d1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ItemKey


`ItemKey` specifies a unique key for a Favorite bar item in Internet Explorer.

A Favorite can include web content such as links, feeds, web slices, or documents, such as Microsoft Word, Microsoft Excel and Microsoft PowerPoint documents.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>ItemKey</code></p></td>
<td><p>Specifies a unique key for the Favorite bar item.</p>
<p><code>ItemKey</code> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FavoriteBarItems](microsoft-windows-ie-internetexplorer-favoritebaritems.md) | [FavoriteBarItem](microsoft-windows-ie-internetexplorer-favoritebaritems-favoritebaritem.md) | **ItemKey**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML example shows three Favorite bar items.

```
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

 

 







