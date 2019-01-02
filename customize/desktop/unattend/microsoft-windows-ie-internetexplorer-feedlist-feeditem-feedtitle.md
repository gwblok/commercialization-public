---
title: FeedTitle
description: FeedTitle
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 21397282-43fd-4790-a5c9-b316f948c522
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FeedTitle


`FeedTitle` specifies the title of a [FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Feed_title</em></p></td>
<td><p>Specifies the title of the <a href="microsoft-windows-ie-internetexplorer-feedlist-feeditem.md" data-raw-source="[FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md)">FeedItem</a>. <em>Feed_title</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FeedList](microsoft-windows-ie-internetexplorer-feedlist.md) | [FeedItem](microsoft-windows-ie-internetexplorer-feedlist-feeditem.md) | **FeedTitle**

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

 

 







