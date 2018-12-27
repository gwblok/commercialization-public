---
title: PromotedIcon1
description: PromotedIcon1
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6b24fbd2-5050-4b18-9f81-9b9ba7954fb6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PromotedIcon1

`PromotedIcon1` specifies an icon to be shown in the visible system notification area on the taskbar in place of the **Action Center** icon.

Up to four system notification icons are shown in the visible portion of the system notification area on the desktop. By default, these icons are **Action Center**, **Battery**—if the system hardware includes battery support—**Network**, and **Volume**.

By setting the **PromotedIcon1** component, you can select another icon to be visible in the system notification area. This icon will appear in place of the **Action Center** icon.

To select the icon to be visible, you must:

* Select an application file that includes a system notification icon. This application file must be signed.
* Set both the **Path** and **GUID** elements for the file.

For information about specifying the GUID for your icon, see [NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [GUID](microsoft-windows-shell-setup-notificationarea-promotedicon1-guid.md) | Specifies the GUID of the icon to be displayed in the notification area. |
| [Path](microsoft-windows-shell-setup-notificationarea-promotedicon1-path.md) | Specifies the path to the application that contains the icon. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | **PromotedIcon1**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to promote a new system notification icon to be visible in place of the **Action Center** icon.

```XML
  <PromotedIcon1>
    <Path>%PROGRAMFILES%\Fabrikam\Application1.exe</Path>
    <GUID>{d8742dcb-3e6a-4b3c-b3fe-374623cdcf06}</GUID>
  </PromotedIcon1>
```

## Related topics

[NotificationArea](microsoft-windows-shell-setup-notificationarea.md)
