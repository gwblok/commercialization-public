---
title: ScreenSaver
description: ScreenSaver
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 49a2e156-f277-4f3b-9d92-d630bb510143
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# ScreenSaver

> [!Important]
> ScreenSaver functionality in Themes is removed. ScreenSaver is deprecated in Group Policy, Control Panel, and SysPrep. Lockscreen features and policies are preferred over using ScreenSaver. We recommend using automatic power plans to dim the screen. This can help reduce system power consumption.

`ScreenSaver` specifies the path to a Windows screen saver file in a theme.

## Values

| Value                    | Description                                                                                                           |
|:-------------------------|:----------------------------------------------------------------------------------------------------------------------|
| *Screen_saver_file*      | Specifies the name of the screen saver file. *Screen_saver_file* is a string with a maximum length of 256 characters. |

## Valid Configuration Passes

specialize

auditSystem

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [Themes](microsoft-windows-shell-setup-themes.md) | **ScreenSaver**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## Related topics

[Themes](microsoft-windows-shell-setup-themes.md)
