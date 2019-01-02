---
title: ShowInformationBar
description: ShowInformationBar
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e8fd7e9f-c08c-46a2-aa40-51ac82342385
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ShowInformationBar


`ShowInformationBar` specifies whether to show the **Information** bar when a pop-up window is blocked.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Shows the <strong>Information</strong> bar when a pop-up window is blocked. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not show the <strong>Information</strong> bar when a pop-up window is blocked.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **ShowInformationBar**

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

 

 







