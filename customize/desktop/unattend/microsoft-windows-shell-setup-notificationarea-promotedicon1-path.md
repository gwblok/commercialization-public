---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e3d92574-5ed4-423f-92f2-4340ef7f4948
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path to an application. This application should contain an icon to be shown in the visible system notification area on the taskbar.

By setting the **Path** and [GUID](microsoft-windows-shell-setup-notificationarea-promotedicon1-guid.md) elements of the **PromotedIcon1** component, you can configure another icon to be visible in the system notification area. This icon will appear in place of the **Action Center** icon.

To select the icon to be visible, you must:

-   Select a signed binary application file that includes a system notification icon.

-   Set both the **Path** and **GUID** elements for the file.

For information about finding the path and GUID for your icon, see [NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Path</p></td>
<td><p>Specifies the path of an icon to be shown in the visible system notification area on the taskbar.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | [PromotedIcon1](microsoft-windows-shell-setup-notificationarea-promotedicon1.md) | **Path**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to promote a new system notification icon to be visible in place of the **Action Center** icon.

```
<NotificationArea>
  <PromotedIcon1>
    <Path>%PROGRAMFILES%\Fabrikam\Application1.exe</Path>
    <GUID>{d8742dcb-3e6a-4b3c-b3fe-374623cdcf06}</GUID>
  </PromotedIcon1>
</NotificationArea>
```

## Related topics


[PromotedIcon1](microsoft-windows-shell-setup-notificationarea-promotedicon1.md)

[GUID](microsoft-windows-shell-setup-notificationarea-promotedicon1-guid.md)

[NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340)

 

 







