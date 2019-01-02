---
title: PlaySound
description: PlaySound
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 473fd27f-54f3-4dea-a07d-ec7689cc90e5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PlaySound


`PlaySound` specifies whether to play a sound when a pop-up window is blocked.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Plays a sound when a pop-up window is blocked. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not play a sound when a pop-up window is blocked.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **PlaySound**

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

 

 







