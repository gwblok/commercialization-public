---
title: FilterLevel
description: FilterLevel
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ca57f9b5-8a2b-47e7-9ebe-cfc7fb6e1a7d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FilterLevel


`FilterLevel` specifies the level of filtering by the Pop-up Blocker.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Low</strong></p></td>
<td><p>Enables pop-up windows from security-enhanced sites.</p></td>
</tr>
<tr class="even">
<td><p><strong>Medium</strong></p></td>
<td><p>Blocks most automatic pop-up windows. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>High</strong></p></td>
<td><p>Blocks all pop-up windows.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **FilterLevel**

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

 

 







