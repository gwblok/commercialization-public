---
title: FeedKey
description: FeedKey
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4e73ca84-7444-47e1-af79-e332c322d47b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FeedKey


`FeedKey` specifies a unique string for a [FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique string for the <a href="microsoft-windows-ie-internetexplorer-feedlist-feeditem.md" data-raw-source="[FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md)">FeedItem</a>.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FeedList](microsoft-windows-ie-internetexplorer-feedlist.md) | [FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md) | **FeedKey**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to set a [FeedList](microsoft-windows-ie-internetexplorer-feedlist.md).

```
<FeedList>
   <FeedItem wcm:action="add">
      <FeedKey>Feed1</FeedKey>
      <FeedTitle>My Feed 1</FeedTitle>
      <FeedURL>http://www.fabrikam.com/rss1</FeedURL>
   </FeedItem>
   <FeedItem wcm:action="add">
      <FeedKey>Feed2</FeedKey>
      <FeedTitle>My Feed 2</FeedTitle>
      <FeedURL>http://www.fabrikam.com/rss2</FeedURL>
   </FeedItem>
</FeedList>
```

## Related topics


[FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md)

 

 







