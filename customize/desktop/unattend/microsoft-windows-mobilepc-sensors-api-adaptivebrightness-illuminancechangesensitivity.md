---
title: IlluminanceChangeSensitivity
description: IlluminanceChangeSensitivity
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9b1eeef3-a892-43c1-92eb-7e16af786fa5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IlluminanceChangeSensitivity


The `IlluminanceChangeSensitivity` specifies the percentage change in illuminance (lux) required to cause a change in display brightness. This is specified in percentage change since the last change in display brightness.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>percent_of_change_in_lux_detected</em></p></td>
<td><p>Specifies the minimum percentage change in lux required to cause a change in display brightness.</p>
<p><em>percent_of_change_in_lux_detected</em> is an integer between 1 and 100. The default value is 10 (10% change in lux).</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)| [AdaptiveBrightness](microsoft-windows-mobilepc-sensors-api-adaptivebrightness.md) | **IlluminanceChangeSensitivity**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md).

## XML Example


The following sample XML output shows how to specify that a minimum of a 20% change in lux is required to cause a change in display brightness.

```
<ALRCurveVersion>2</ALRCurveVersion>
<ALRPoints>000000000a0000000a00000028000000280000005000000044</ALRPoints>
<DisplayResponseInterval>60000</DisplayResponseInterval>
<IlluminanceChangeSensitivity>20</IlluminanceChangeSensitivity>
```

## Related topics



[ALRCurveVersion](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-alrcurveversion.md)

[ALRPoints](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-alrpoints.md)

[DisplayResponseInterval](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-displayresponseinterval.md)

