---
title: AllowedSites
description: AllowedSites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bae4ed91-71b0-4c1a-8a69-bdf68b442723
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AllowedSites


`AllowedSites` specifies the Internet sites that the Pop-up Blocker enables to use pop-up windows.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_url</em></p></td>
<td><p>Specifies the fully qualified path to the URL of each Internet site that Pop-up Blocker enables to use pop-up windows. You can add multiple sites by using semi-colons as the separator. <em>Path_to_url</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **AllowedSites**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure the Pop-up Blocker.

```
<AllowedSites>http://www.fabrikam.com;http://www.contoso.com</AllowedSites>
<FilterLevel>High</FilterLevel> 
<PlaySound>false</PlaySound> 
<ShowInformationBar>false</ShowInformationBar>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







