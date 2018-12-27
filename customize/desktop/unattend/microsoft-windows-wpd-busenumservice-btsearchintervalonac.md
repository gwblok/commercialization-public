---
title: BTSearchIntervalOnAC
description: BTSearchIntervalOnAC
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e1adcb7f-6310-4067-b828-652f19cda601
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BTSearchIntervalOnAC


`BTSearchIntervalOnAC` specifies how often the computer will search for other devices using Media Transfer Protocol over Bluetooth *(MTP/BT)*, while plugged in.

By default, the computer searches for devices that have been paired and enabled for the MTP/BT service. While the computer is plugged in to AC power, it will perform this search every 120 seconds.

If `BTSearchIntervalOnAC` is set to **0**, then the computer will not search for these devices while it is plugged in to AC power.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>BTSearchIntervalOnAC</code></p></td>
<td><p>Specifies how often the computer will search for portable devices using MTP/BT while plugged in to AC power.</p>
<p><code>BTSearchIntervalOnAC</code> is an integer.</p>
<p>The default value is 120 seconds.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-WPD-BusEnumService](microsoft-windows-wpd-busenumservice.md) | **BTSearchIntervalOnAC**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-WPD-BusEnumService](microsoft-windows-wpd-busenumservice.md).

## XML Example


The following XML output specifies that the system will search for MTP/BT portable devices every 60 seconds while plugged in to AC power, and will not search for MTP/BT portable devices while on battery power:

```
<BTSearchIntervalOnAC>60</BTSearchIntervalOnAC>
<BTSearchIntervalOnDC>0</BTSearchIntervalOnDC>
```

## Related topics


[BTSearchIntervalOnDC](microsoft-windows-wpd-busenumservice-btsearchintervalondc.md)

 

 







