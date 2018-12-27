---
title: QuickLinkName
description: QuickLinkName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6d1c32cd-87dd-434e-9838-2d459adede18
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# QuickLinkName


`QuickLinkName` specifies a friendly name for the [QuickLinkItem](microsoft-windows-ie-internetexplorer-quicklinklist-quicklinkitem.md), as it appears on the **Favorites** toolbar.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name_of_site</em></p></td>
<td><p>Specifies the friendly name of a site, as it appears on the <strong>Favorites</strong> toolbar. <em>Name_of_site</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [QuickLinkList](microsoft-windows-ie-internetexplorer-quicklinklist.md) | [QuickLinkItem](microsoft-windows-ie-internetexplorer-quicklinklist-quicklinkitem.md) | **QuickLinkName**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure a [QuickLinkList](microsoft-windows-ie-internetexplorer-quicklinklist.md).

```
<QuickLinkList>
   <QuickLinkItem>
      <QLID>0</QLID>
      <QuickLinkUrl>http://www.fabrikam.com/QL.htm</QuickLinkUrl>
      <QuickLinkName>Fabrikam Quick Link</QuickLinkName>
   </QuickLinkItem>
   <QuickLinkItem>
      <QLID>1</QLID>
      <QuickLinkUrl>http://www.fabrikam.com/QL2.htm</QuickLinkUrl>
      <QuickLinkName>Fabrikam Quick Link 2</QuickLinkName>
   </QuickLinkItem>
</QuickLinkList>
```

## Related topics


[QuickLinkItem](microsoft-windows-ie-internetexplorer-quicklinklist-quicklinkitem.md)

 

 







