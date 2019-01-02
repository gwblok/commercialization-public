---
title: StartPages
description: StartPages
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dfe41935-694e-46c9-ab1a-615706399d1c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# StartPages

The `StartPages` setting specifies additional home pages opened when tabbed browsing is enabled.

To set the primary home page, use the [Home\_Page](microsoft-windows-ie-internetexplorer-home-page.md) setting. If you set **StartPages**, and do not set the Home\_Page setting, then the default MSN home page will appear as the first home page.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [StartPage](microsoft-windows-ie-internetexplorer-startpages-startpage.md) | Specifies a tabbed browsing home page. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **StartPages**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set a primary home page and two secondary home pages.

```XML
<Home_Page>http://www.fabrikam.com</Home_Page>
<StartPages>
   <StartPage>
      <StartPageKey>StartPage1</StartPageKey>
      <StartPageUrl>http://www.fabrikam.com/news</StartPageUrl>
   </StartPage>
   <StartPage>
      <StartPageKey>StartPage2</StartPageKey>
      <StartPageUrl>http://www.contoso.com</StartPageUrl>
   </StartPage>
</StartPages>
```

## Related topics

[Home\_Page](microsoft-windows-ie-internetexplorer-home-page.md)

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)
