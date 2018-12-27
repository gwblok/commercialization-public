---
title: StartPage
description: StartPage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1ceec680-17ea-4730-ae2d-afe5f1509e1d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# StartPage

`StartPage` specifies a tabbed browsing start page. If you set `StartPages`, and do not set `Home_Page`, then the default MSN home page will appear as the first home page. For the primary home page, see the [Home\_Page](microsoft-windows-ie-internetexplorer-home-page.md) setting.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [StartPageKey](microsoft-windows-ie-internetexplorer-startpages-startpage-startpagekey.md) | Specifies a unique string for a start page. |
| [StartPageUrl](microsoft-windows-ie-internetexplorer-startpages-startpage-startpageurl.md) | Specifies the URL of a start page. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [StartPages](microsoft-windows-ie-internetexplorer-startpages.md) | **StartPage**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set secondary start pages.

```XML
<StartPages>
   <StartPage>
      <StartPageKey>StartPage1</StartPageKey>
      <StartPageUrl>http://www.fabrikam.com</StartPageUrl>
   </StartPage>
   <StartPage>
      <StartPageKey>StartPage2</StartPageKey>
      <StartPageUrl>http://www.contoso.com</StartPageUrl>
   </StartPage>
</StartPages>
```

## Related topics

[StartPages](microsoft-windows-ie-internetexplorer-startpages.md)
