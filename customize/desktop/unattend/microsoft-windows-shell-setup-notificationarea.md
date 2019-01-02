---
title: NotificationArea
description: NotificationArea
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a2c2649d-3d85-4823-9e5b-a5d17279e52f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# NotificationArea

`NotificationArea` manages settings related to the notification area of the taskbar.

Four notification icons are shown in the visible portion of the notification area on the desktop. By default, these icons are **Action Center**, **Battery**—if the system hardware includes battery support—**Network**, and **Volume**.

You can select up to two other icons to be visible in the notification area. These other icons will appear in place of the **Action Center** and **Battery** icons.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [PromotedIcon1](microsoft-windows-shell-setup-notificationarea-promotedicon1.md) | Specifies an icon to be visible in the notification area in place of the <strong>Action Center</strong> icon. |
| [PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md) | Specifies an icon to be visible in the notification area in place of the <strong>Battery</strong> icon. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **Notification Area**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to promote two other notification icons to be visible in place of the **Action Center** and **Battery** icons.

```XML
<NotificationArea>
  <PromotedIcon1>
    <Path>%PROGRAMFILES%\Fabrikam\Application1.exe</Path>
    <GUID>{d8742dcb-3e6a-4b3c-b3fe-374623cdcf06}</GUID>
  </PromotedIcon1>
  <PromotedIcon2>
    <Path>%PROGRAMFILES%\Fabrikam\Application2.exe</Path>
    <GUID>{a1bc23cb-3456-bcde-abcd-feb363cacc88}</GUID>
  </PromotedIcon2>
</NotificationArea>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
