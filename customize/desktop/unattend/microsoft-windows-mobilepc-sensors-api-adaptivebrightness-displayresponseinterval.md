---
title: DisplayResponseInterval
description: DisplayResponseInterval specifies the minimum time between changes in display brightness due to changes in lighting conditions.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ea943baf-331b-41f4-b64f-e2808f432a1d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisplayResponseInterval


`DisplayResponseInterval` specifies the minimum time between changes in display brightness due to changes in lighting conditions.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>time_in_milliseconds</em></p></td>
<td><p>Specifies the minimum time, in milliseconds, between changes in display brightness due to changes in lighting conditions.</p>
<p><em>time_in_milliseconds</em> is an integer between 100 (0.1 seconds) and 36000000 (1 hour). The default value is 2000 (2 seconds).</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)| [AdaptiveBrightness](microsoft-windows-mobilepc-sensors-api-adaptivebrightness.md) | **DisplayResponseInterval**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md).

## XML Example


This XML example shows how to set the minimum time between changes in display brightness due to changes in lighting conditions to one minute.

```
<ALRCurveVersion>2</ALRCurveVersion>
<ALRPoints>000000000a0000000a00000028000000280000005000000044</ALRPoints>
<DisplayResponseInterval>60000</DisplayResponseInterval>
<IlluminanceChangeSensitivity>20</IlluminanceChangeSensitivity>
```

## Related topics


[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)

[IlluminanceChangeSensitivity](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-illuminancechangesensitivity.md)

[ALRPoints](microsoft-windows-mobilepc-sensors-api-adaptivebrightness-alrpoints.md)

 

 







