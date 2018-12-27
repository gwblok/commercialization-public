---
title: TelemetryPerformanceHighResolutionTimer
description: Enables high resolution timer for hourly IO latency summaries in Storport event logs.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 92FE5078-B8CA-4877-B18E-632F9F663857


ms.date: 05/02/2017
ms.topic: article


---

# TelemetryPerformanceHighResolutionTimer

> [!Important]
> This setting is removed from Unattend in Windows 10, version 1803.

Enables high resolution timer for hourly IO latency summaries in Storport event logs.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the high resolution timer is used. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that a lower resolution timer is used.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

auditSystem

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-StorePort-RegistrySettings](microsoft-windows-storport-registrysettings.md) | **TelemetryPerformanceHighResolutionTimer**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-StorPort-RegistrySettings](microsoft-windows-storport-registrysettings.md).

 

 






