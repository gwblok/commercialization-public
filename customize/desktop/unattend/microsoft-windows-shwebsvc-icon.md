---
title: Icon
description: Icon
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: af7616ea-9f09-4d4d-a0e5-d439df2bb02d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Icon


`Icon` specifies the path to and the file name of the icon file for the online printing company website to display in the Online Print Wizard. Whenever it is possible, provide the absolute path to the icon that is stored on the user's hard disk. This will ensure that the Photo Gallery in the desktop can display the icon the first time that Photo Gallery in the desktop is used.

If the absolute path cannot be provided, provide the URL to the icon file hosted on the Web. In this case, the first time Photo Gallery in the desktop is launched, the default Online Print Wizard icon will be used until the icon is downloaded.

If the provider is a Microsoft partner, and the icon is hosted on the Microsoft website, then this setting can be just the file name of the icon.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Icon</em></p></td>
<td><p>Specifies the path and the file name of the icon for the online printing company to display in the Online Print Wizard. <em>Icon</em> is a string. The .ico file must be present on the installed Windows operating system.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md) | **Icon**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md).

## XML Example


The following XML output shows how to set Lucerne Publishing for online printing.

```
<Description>Get photos printed by Lucerne and delivered to your home.</Description>
<DisplayName>Lucerne Publishing</DisplayName>
<href>lucernepublishing.com</href>
<Icon>c:\Lucerne\lucernepub.ico</Icon>
<ID>lucernepub</ID>
```

## Related topics


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md)

 

 







