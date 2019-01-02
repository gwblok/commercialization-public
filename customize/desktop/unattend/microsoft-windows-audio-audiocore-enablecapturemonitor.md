---
title: EnableCaptureMonitor
description: EnableCaptureMonitor
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3a407d2a-c732-4f61-8ccd-67cef5e1979f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableCaptureMonitor


`EnableCaptureMonitor` specifies whether Windows includes an option to play audio from devices connected to the **Audio In** port. The computer actively detects whether a device is connected to an **Audio In** port.

If this option is enabled, then the end user can configure the system to play audio from a device. For example, the end user can plug in a portable music player and listen to music through the computer speakers.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Specifies that end users can configure the system to play audio from a device connected to an <strong>Audio In</strong> port.</p>
<p>This is the default value</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Specifies that end users cannot configure the system to play audio from a device connected to an <strong>Audio In</strong> port.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Audio-AudioCore](microsoft-windows-audio-audiocore.md) | **EnableCaptureMonitor**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Audio-VolumeControl](microsoft-windows-audio-volumecontrol.md).

## XML Example


The following XML output specifies that an end user cannot configure the system to play audio from a device connected to an **Audio In** port.

```
<EnableCaptureMonitor>false</EnableCaptureMonitor>
```

## Related topics


[Microsoft-Windows-Audio-AudioCore](microsoft-windows-audio-audiocore.md)

 

 







