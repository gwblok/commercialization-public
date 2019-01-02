---
title: Microsoft-Windows-CodeIntegrity
description: Microsoft-Windows-CodeIntegrity
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 04/30/2018
ms.topic: article
ms.custom: RS5
---
# Microsoft-Windows-CodeIntegrity

The `Microsoft-Windows-CodeIntegrity` component is new in Windows 10, version 1803. Use the `SKUPolicyRequired` setting to indicate whether a Windows 10 device will run in S mode on next boot.

S mode can be applied to a Windows 10 Home, Pro, Pro EDU, or Pro WS edition to enable a productive user experience that's streamlined for security. Windows 10 in S mode supports using apps from the Microsoft Store only, and supports web browsing only in the Microsoft Edge browser. In previous versions of Windows, Windows 10 S was a separate edition that required working with a different Windows image than non-S editions. Starting with Windows 10, version 1803, you can enable S mode on supported Windows editions.

For more on Windows 10 in S mode, including the specifics of which apps and programs are supported, manufacturing and design considerations, and instructions for applying the Unattend file to the image using DISM, see the [Windows 10 in S mode manufacturing overview](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-10-s-overview).

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [SKUPolicyRequired](microsoft-windows-codeintegrity-skupolicyrequired.md) | New in Windows 10, version 1803. This setting indicates whether a Windows 10 device is running in S mode. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)

[Windows 10 in S mode manufacturing overview](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-10-s-overview)
