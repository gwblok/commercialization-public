---
title: IsAutobrightnessEnabledByDefault
description: IsAutobrightnessEnabledByDefault specifies whether autobrightness is enabled by default.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/02/2018
ms.topic: article
ms.prod: windows - hardware
ms.technology: windows - oem
ms.custom: RS5
---

# IsAutobrightnessEnabledByDefault


IsAutobrightnessEnabledByDefault specifies whether autobrightness is enabled by default. This setting only applies to nits-based systems. It is ignored on percentage based systems.

When this setting is false, use [DefaultSliderPosition](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-defaultsliderposition.md) to set the default brightness level.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| true                    | Autobrightness is enabled by default. |
| false                   | Autobrightness is not enabled by default.  |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-MobilePC-Sensors-API-AdaptiveBrightness](microsoft-windows-mobilepc-sensors-api-adaptivebrightness.md) | **IsAutobrightnessEnabledByDefault**

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## XML Example

```XML
<IsAutobrightnessEnabledByDefault>false</IsAutobrightnessEnabledByDefault>
<DefaultSliderPercentage>75</DefaultSliderPercentage>
```

## Related Topics

[Microsoft-Windows-MobilePC-Sensors-API-AdaptiveBrightness](microsoft-windows-mobilepc-sensors-api-adaptivebrightness.md)
