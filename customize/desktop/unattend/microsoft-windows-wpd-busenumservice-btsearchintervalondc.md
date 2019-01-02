---
title: BTSearchIntervalOnDC
description: BTSearchIntervalOnDC
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c34d3d19-1715-4554-933e-e322000258bb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BTSearchIntervalOnDC


`BTSearchIntervalOnDC` specifies how often the computer will search for other devices using Media Transfer Protocol over Bluetooth *(MTP/BT)*, while on battery power.

By default, the computer will search for devices that have been paired and enabled for the MTP/BT service. While the computer is on battery power, it will perform this search every 240 seconds.

If `BTSearchIntervalOnDC` is set to **0**, then the computer will not search for these devices while the computer is on battery power.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>BTSearchIntervalOnDC</code></p></td>
<td><p>Specifies how often the computer will search for portable devices using MTP/BT while on battery power.</p>
<p><code>BTSearchIntervalOnDC</code> is an integer.</p>
<p>The default value is 240 seconds.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-WPD-BusEnumService](microsoft-windows-wpd-busenumservice.md) | **BTSearchIntervalOnDC**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-WPD-BusEnumService](microsoft-windows-wpd-busenumservice.md).

## XML Example


The following XML output specifies that the system will search for MTP/BT portable devices every 60 seconds while plugged in to AC power, and will not search for MTP/BT portable devices while on battery power:

```
<BTSearchIntervalOnAC>60</BTSearchIntervalOnAC>
<BTSearchIntervalOnDC>0</BTSearchIntervalOnDC>
```

## Related topics


[BTSearchIntervalOnAC](microsoft-windows-wpd-busenumservice-btsearchintervalonac.md)

 

 







