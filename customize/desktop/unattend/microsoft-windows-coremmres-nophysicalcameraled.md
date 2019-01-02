---
title: NoPhysicalCameraLED
description: NoPhysicalCameraLED
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9bd9c1a1-b9d6-474b-a22d-cf428c90a731
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# NoPhysicalCameraLED


`NoPhysicalCameraLED` indicates that there is no physical LED for the device’s camera. An example of a physical LED for a camera is the small blue light that turns on whenever the camera is streaming video. This setting is used to indicate to the shell component that it will need to provide a small indicator in the user interface (UI) to show when video frames are streaming or not streaming to replace the notification by physical LED.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Does not draw an indicator in the UI to show when the camera is on or off. Instead, a physical LED exists to show when video frames are streaming or not streaming.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Draws an indicator in the UI to show when video frames are streaming or not streaming.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md) | **NoPhysicalCameraLED**

## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

generalize

specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md).

## XML Example


The following XML output specifies that no physical camera LED exists for the device.

```
< NoPhysicalCameraLED >1</ NoPhysicalCameraLED >
```

## Related topics


[Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md)

 

 







