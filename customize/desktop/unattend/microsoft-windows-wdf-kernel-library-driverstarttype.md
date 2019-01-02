---
title: DriverStartType
description: DriverStartType
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cd91a4e0-82d6-486d-ac29-fc93531d89b7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DriverStartType


`DriverStartType` specifies whether the Kernel-Mode Driver Framework (KMDF) service is started at boot or on demand.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that the service starts immediately when the computer is started. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>3</strong></p></td>
<td><p>Specifies that the service can start on demand. This applies only if there are no boot-start KMDF drivers on the system. Otherwise, the system can be rendered unbootable.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-WDF-Kernel Library](microsoft-windows-wdf-kernel-library.md) | **DriverStartType**

## Valid Configuration Passes


offlineServicing

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-WDF-Kernel Library](microsoft-windows-wdf-kernel-library.md).

## XML Example


The following XML output shows how to set the service to start on demand.

```
<DriverStartType>3</DriverStartType>
```

## Related topics


[Microsoft-Windows-WDF-Kernel Library](microsoft-windows-wdf-kernel-library.md)

 

 







