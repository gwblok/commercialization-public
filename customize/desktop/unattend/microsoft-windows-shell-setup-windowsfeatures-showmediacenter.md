---
title: ShowMediaCenter
description: ShowMediaCenter
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ed2a8ad7-48e3-47ec-9dff-e11df3047991
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ShowMediaCenter


`ShowMediaCenter` specifies whether to show entry points for Windows Media Center.

This setting has no effect on Server Core installations.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that entry points for Windows Media Center are displayed. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that entry points for Windows Media Center are not displayed.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [WindowsFeatures](microsoft-windows-shell-setup-windowsfeatures.md) | **ShowMediaCenter**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to specify that the entry points for these Windows features not be displayed.

```
<WindowsFeatures>
   <ShowInternetExplorer>false</ShowInternetExplorer>
   <ShowMediaCenter>false</ShowMediaCenter>
   <ShowWindowsMediaPlayer>false</ShowWindowsMediaPlayer>
   <ShowWindowsMail>false</ShowWindowsMail>
</WindowsFeatures>
```

## Related topics


[WindowsFeatures](microsoft-windows-shell-setup-windowsfeatures.md)

 

 







