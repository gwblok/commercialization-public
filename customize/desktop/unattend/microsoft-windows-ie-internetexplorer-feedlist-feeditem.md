---
title: FeedItem
description: FeedItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2e055876-3e09-4dbd-9682-e8660f489d91
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FeedItem

`FeedItem` specifies a Web feed to be received on the computer.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FeedKey](microsoft-windows-ie-internetexplorer-feedlist-feeditem-feedkey.md) | Specifies a unique string for a <code>FeedItem</code>. |
| [FeedTitle](microsoft-windows-ie-internetexplorer-feedlist-feeditem-feedtitle.md) | Specifies the title of a <code>FeedItem</code>. |
| [FeedURL](microsoft-windows-ie-internetexplorer-feedlist-feeditem-feedurl.md) | Specifies the URL of a <code>FeedItem</code>. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [FeedList](microsoft-windows-ie-internetexplorer-feedlist.md) | **FeedItem**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set a [FeedList](microsoft-windows-ie-internetexplorer-feedlist.md).

```XML
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

[FeedList](microsoft-windows-ie-internetexplorer-feedlist.md)
