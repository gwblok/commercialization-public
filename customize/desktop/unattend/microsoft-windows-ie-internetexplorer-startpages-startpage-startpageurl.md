---
title: StartPageUrl
description: StartPageUrl
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 74cdf9dd-f1f6-4f68-bb70-02e788f78bfd
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# StartPageUrl


`StartPageUrl` specifies the URL of a start page. If you set `StartPages`, and do not set `Home_Page`, then the default MSN home page will appear as the first home page. For the primary home page, see the [Home\_Page](microsoft-windows-ie-internetexplorer-home-page.md) setting.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>URL</em></p></td>
<td><p>Specifies the URL of a start page. <em>URL</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [StartPages](microsoft-windows-ie-internetexplorer-startpages.md) | [StartPage](microsoft-windows-ie-internetexplorer-startpages-startpage.md) | **StartPageUrl**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to set secondary start pages.

```
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


[StartPage](microsoft-windows-ie-internetexplorer-startpages-startpage.md)

 

 







