---
title: Microsoft-Windows-Embedded-EmbeddedLogon
description: You can use custom logon to suppress UI elements that relate to the Welcome screen and shutdown screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: F4A7FB96-C9FE-4463-B877-150F0F31D259
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-Embedded-EmbeddedLogon

You can use custom logon to suppress UI elements that relate to the Welcome screen and shutdown screen. For example, you can suppress all elements of the Welcome screen UI and provide a custom logon UI. You can also suppress the blocked shutdown resolver (BSDR) screen and automatically end applications while the OS waits for apps to close before a shutdown.

Custom logon settings do not modify the credential behavior of Winlogon, so you can use any credential provider that is compatible with the OS to provide a custom sign-in experience for your device.

You cannot change the configuration of custom logon during runtime.

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AnimationDisabled](microsoft-windows-embedded-embeddedlogon-animationdisabled.md) | Disables the Welcome screen transition animation for custom logon |
| [BrandingNeutral](microsoft-windows-embedded-embeddedlogon-brandingneutral.md) | Specifies which UI elements display on the Welcome screen. |
| [HideAutoLogonUI](microsoft-windows-embedded-embeddedlogon-hideautologonui.md) | Hides the Welcome screen when automatic sign-in is enabled. |
| [NoLockScreen](microsoft-windows-embedded-embeddedlogon-nolockscreen.md) | Disables the lock screen functionality and UI elements. |
| [UIVerbosityLevel](microsoft-windows-embedded-embeddedlogon-uiverbositylevel.md) | Disables the Windows status messages during device startup, sign-in, and shut down. |

## Applies to

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).
