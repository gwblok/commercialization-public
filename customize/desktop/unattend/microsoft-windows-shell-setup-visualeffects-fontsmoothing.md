---
title: FontSmoothing
description: FontSmoothing
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 841603b8-abd8-48a3-8445-9ee27da1b254
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# FontSmoothing

> [!Important]
> This setting is now deprecated.

`FontSmoothing` specifies whether font smoothing is enabled, and which type.

This setting has no effect on Server Core installations.

## Values

| Value             | Description                                                                      |
|:------------------|:---------------------------------------------------------------------------------|
| **Standard**      | Specifies that the computer chooses the setting, based on a performance test.    |
| **On**            | Specifies that font smoothing is turned on.                                      |
| **Off**           | Specifies that font smoothing is turned off.                                     |
| **ClearType**     | Specifies that Clear Type is used for font smoothing.                            |

This string type supports empty elements.

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [VisualEffects](microsoft-windows-shell-setup-visualeffects.md) | **FontSmoothing**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## Related topics

[VisualEffects](microsoft-windows-shell-setup-visualeffects.md)
