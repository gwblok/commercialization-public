---
title: Microsoft-Windows-Embedded-BootExp
description: You can use the settings in Microsoft-Windows-Embedded-BootExp to suppress OS elements that appear when the device starts or resumes, or you can suppress the crash screen when the OS encounters an error that it cannot recover from.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 97A8CEC7-2F28-4D76-9BE3-DEBEE85E027C
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-Embedded-BootExp

You can use the settings in `Microsoft-Windows-Embedded-BootExp` to suppress OS elements that appear when the device starts or resumes, or you can suppress the crash screen when the OS encounters an error that it cannot recover from.

Unbranded boot can also be configured at runtime.

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DisableBootMenu](microsoft-windows-embedded-bootexp-disablebootmenu.md) | Disables the F8 and F10 keys during startup to prevent access to the <strong>Advanced Startup Options</strong> menu. |
| [DisplayDisabled](microsoft-windows-embedded-bootexp-displaydisabled.md) | Configures the device to display a blank screen when the OS encounters an error that it cannot recover from. |
| [HideAllBootUI](microsoft-windows-embedded-bootexp-hideallbootui.md) | Suppresses all Windows UI elements (logo, status indicator, and status message) during startup. |
| [HideBootLogo](microsoft-windows-embedded-bootexp-hidebootlogo.md) | Suppresses the default Windows logo that displays during the OS loading phase. |
| [HideBootStatusIndicator](microsoft-windows-embedded-bootexp-hidebootstatusindicator.md) | Suppresses the status indicator that displays during the OS loading phase. |
| [HideBootStatusMessage](microsoft-windows-embedded-bootexp-hidebootstatusmessage.md) | Suppresses the startup status text that displays during the OS loading phase. |

## Applies to

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).
