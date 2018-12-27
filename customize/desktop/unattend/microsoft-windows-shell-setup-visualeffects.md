---
title: VisualEffects
description: VisualEffects
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1bea22d2-6279-4d0f-8019-f8885cbdec72
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 04/30/2018
ms.topic: article


---
# VisualEffects

> [!Important]
> This component is deprecated.

`VisualEffects` specifies additional display settings.

This setting has no effect on Server Core installations.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FontSmoothing](microsoft-windows-shell-setup-visualeffects-fontsmoothing.md) | **This setting has been deprecated**. Specifies whether font smoothing is enabled, and which type of font smoothing is enabled. |
| [SystemDefaultBackgroundColor](microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md) | **This setting has been deprecated**. Specifies the system default Windows background color scheme appearing on first boot, and on LogonUI if no user is selected. |

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **VisualEffects**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows **ClearType** enabled for font smoothing.

```XML
<VisualEffects>
   <FontSmoothing>ClearType</FontSmoothing>
</VisualEffects>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
