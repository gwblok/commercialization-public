---
title: ALRPoints
description: ALRPoints
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 21889fef-49ef-4b6d-bc07-2d698c72d789
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ALRPoints

ALRPoints specifies the ambient light response (ALR) curve data.

The curve is defined by the illuminance (lux) detected by an ambient light sensor, and the percentage of change in brightness.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ALR_curve</em>.</p></td>
<td><p>The ambient light curve is a string value. For information on generating an <em>ALR_curve</em> string, see <a href="https://docs.microsoft.com/en-us/windows-hardware/design/whitepapers/integrating-ambient-light-sensors-with-computers-running-windows-10-creators-update" data-raw-source="[Integrating Ambient Light Sensors with Computers Running Windows 10](https://docs.microsoft.com/en-us/windows-hardware/design/whitepapers/integrating-ambient-light-sensors-with-computers-running-windows-10-creators-update)">Integrating Ambient Light Sensors with Computers Running Windows 10</a>.</p></td>
</tr>
</tbody>
</table>

 

The *ALR\_curve* can be also generated manually, using the following format: 00+*Change\_in\_brightness\_1*,*Lux\_measurement\_1*,*Change\_in\_brightness\_2*,*Lux\_measurement\_2*,*Change\_in\_brightness\_3*,*Lux\_measurement\_3* … .

*Change\_in\_brightness* is the percentage of change in brightness based on the display brightness baseline. This is a 8-digit hexadecimal number. For example, 00000096 = 150% of the current brightness level.

*Lux\_measurement* is the illuminance (lux) detected by the ambient light sensor. For example, 000003E8 = 1000 lux.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md) | [AdaptiveBrightness](microsoft-windows-mobilepc-sensors-api-adaptivebrightness.md) | **ALRPoints**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md).

## XML Example


The following sample XML output shows how to set the following ALR curve:

Adjust the screen to 10% of the baseline brightness level when the ambient light sensor detects 10 lux.

Adjust the screen to 40% of the baseline brightness level when the ambient light sensor detects 40 lux.

Adjust the screen to 80% of the baseline brightness level when the ambient light sensor detects 68 lux.

```
<ALRCurveVersion>2</ALRCurveVersion>
<ALRPoints>000000000a0000000a00000028000000280000005000000044</ALRPoints>
<DisplayResponseInterval>60000</DisplayResponseInterval>
<IlluminanceChangeSensitivity>20</IlluminanceChangeSensitivity>
```

## Related topics

[ALRCurveVersion](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-alrcurveversion.md)

[DisplayResponseInterval](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-displayresponseinterval.md)

[IlluminanceChangeSensitivity](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-illuminancechangesensitivity.md)


