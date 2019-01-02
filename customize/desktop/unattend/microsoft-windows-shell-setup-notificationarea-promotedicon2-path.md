---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c9df251b-db0e-4f71-b984-ad95d0370ccb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path to an application. This application should contain an icon to be shown in the notification area at the far right of the taskbar.

By setting the **Path** and [GUID](microsoft-windows-shell-setup-notificationarea-promotedicon2-guid.md) elements of the **PromotedIcon2** component, you can configure another icon to be visible in the notification area. This icon will appear in place of the **Battery** icon.

To select the icon to be visible, you must:

-   Select a signed binary application file that includes a notification-area icon.

-   Set both the **Path** and **GUID** elements for the file.

For information about finding the path and GUID for your icon, see the MSDN topic: [NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Path</p></td>
<td><p>Specifies the path of an icon to be shown in the notification area.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | [PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md) | **Path**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to promote a new notification-area icon to be visible in place of the **Battery** icon.

```
  <PromotedIcon2>
    <Path>%PROGRAMFILES%\Fabrikam\Application2.exe</Path>
    <GUID>{a1bc23cb-3456-bcde-abcd-feb363cacc88}</GUID>
  </PromotedIcon2>
```

## Related topics


[PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md)

[GUID](microsoft-windows-shell-setup-notificationarea-promotedicon2-guid.md)

 

 







