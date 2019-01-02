---
title: PromotedIcon2
description: PromotedIcon2
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3296422c-4803-4f6b-ad54-af820916ec82
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PromotedIcon2

`PromotedIcon2` specifies an icon to be shown in the visible system notification area on the taskbar in place of the **Battery** icon.

Up to four system notification icons are shown in the visible portion of the system notification area on the desktop. By default, these icons are **Action Center**, **Battery**—(if the system hardware includes battery support—**Network**, and **Volume**.

By setting the **PromotedIcon2** component, you can select another icon to be visible in the system notification area. This icon will appear in place of the **Battery** icon.

> [!Note]
> For portable computers, we recommend including a battery indicator that is visible at all times, such as the default **Battery** system notification icon.

To select the icon to be visible, you must:

* Select an application file that includes a system notification icon. This application file must be signed.
* Set both the **Path** and **GUID** elements for the file.

For information about specifying the GUID for your icon, see the MSDN Topic: [NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [GUID](microsoft-windows-shell-setup-notificationarea-promotedicon2-guid.md) | Specifies the GUID of the icon to be displayed in the notification area. |
| [Path](microsoft-windows-shell-setup-notificationarea-promotedicon2-path.md) | Specifies the path to the application that contains the icon. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | **PromotedIcon1**

## Applies To

Windows 8, Windows 7, Windows Server 2012, and Windows Server 2008 R2 editions.

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to promote a new system notification icon to be visible in place of the **Battery** icon.

```XML
  <PromotedIcon2>
    <Path>%PROGRAMFILES%\Fabrikam\Application2.exe</Path>
    <GUID>{a1bc23cb-3456-bcde-abcd-feb363cacc88}</GUID>
  </PromotedIcon2>
```

## Related topics

[NotificationArea](microsoft-windows-shell-setup-notificationarea.md)

[NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340)
