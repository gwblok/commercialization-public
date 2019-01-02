---
title: EnableVolumeControlWhileLocked
description: EnableVolumeControlWhileLocked
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2ac68bb8-da5b-48f5-8e7e-9d0a82db3458
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableVolumeControlWhileLocked


**EnableVolumeControlWhileLocked** specifies whether volume controls appear when the computer is locked.

Example: While the computer is playing music, the user locks the computer. If **EnableVolumeControlWhileLocked** is enabled, then when the computer is locked, the user can adjust or mute the music's volume by using the keyboard or a connected device, without needing to unlock the computer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>When the computer is locked, volume can be changed.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>When the computer is locked, volume cannot be changed.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Audio-VolumeControl](microsoft-windows-audio-volumecontrol.md) | **EnableVolumeControlWhileLocked**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Audio-VolumeControl](microsoft-windows-audio-volumecontrol.md).

## XML Example


The following XML output specifies that volume controls are not available when the computer is locked.

```
<EnableVolumeControlWhileLocked>false</EnableVolumeControlWhileLocked>
```

## Related topics


[Microsoft-Windows-Audio-VolumeControl](microsoft-windows-audio-volumecontrol.md)

 

 







