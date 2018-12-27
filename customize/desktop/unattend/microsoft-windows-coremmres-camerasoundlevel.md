---
title: CameraSoundLevel
description: CameraSoundLevel
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fcfe3b87-53bf-4edc-a5fa-9b324a7d498f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CameraSoundLevel


`CameraSoundLevel` specifies the sound volume that a camera will play when a photo is taken, when a series of photos are taken, or while a video is recorded.

As devices get smaller it is important that bystanders be aware that they are being recorded for privacy purposes. This feature will enable OEMs to set the device to a mode where the sound cannot be bypassed.

You can use this setting to set the device to a mode where the sound is played when a camera is actively recording or taking a photo cannot be bypassed by a user or application.

This feature will make a best effort to provide the restrictions for the camera sound. This setting applies to all Modern video capture applications.

**Note**

Audio effects implemented in Audio Processing Objects (APOs) or in the DSP can sometimes interfere with the implementation of this feature, and could result in the attenuation of the camera sound.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>No sound is played when a user starts a recording, stops a recording, takes a photo or starts a photo sequence.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1-100</p></td>
<td><p>Sets the volume of the sound played when a user starts a recording, stops a recording, takes a photo or starts a photo sequence.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md) | **CameraSoundLevel**

## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

generalize

specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md).

## XML Example


The following XML output specifies that Windows will play a medium volume tone when a photo is taken.

```
<CameraSoundLevel>50</CameraSoundLevel>
```

## Related topics


[Microsoft-Windows-CoreMmRes](microsoft-windows-coremmres.md)

 

 







