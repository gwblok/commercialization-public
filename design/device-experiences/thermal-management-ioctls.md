---
title: Thermal Management IOCTLs
description: This topic discusses the input/output controls (IOCTLs) that are used for Thermal Management in Windows.
MS-HAID:
- 'cstandby.thermal\_management\_ioctls'
- 'p\_weg\_hardware.thermal\_management\_ioctls'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0B767145-1132-467C-8077-AF913844D7DD

ms.date: 05/02/2017
ms.topic: article


---

# Thermal Management IOCTLs


This topic discusses the input/output controls (IOCTLs) that are used for Thermal Management in Windows.

Driver implementers need to implement responses to the following input/output (I/O) control codes.

## In this section


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="ioctl-thermal-read-policy.md" data-raw-source="[IOCTL_THERMAL_READ_POLICY](ioctl-thermal-read-policy.md)">IOCTL_THERMAL_READ_POLICY</a></p></td>
<td><p>The <a href="ioctl-thermal-read-policy.md" data-raw-source="[IOCTL_THERMAL_READ_POLICY](ioctl-thermal-read-policy.md)">IOCTL_THERMAL_READ_POLICY</a> I/O control request is sent by the kernel to a thermal zone’s policy driver to read the drivers&#39; preferred policy.</p></td>
</tr>
<tr class="even">
<td><p><a href="ioctl-thermal-read-temperature.md" data-raw-source="[IOCTL_THERMAL_READ_TEMPERATURE](ioctl-thermal-read-temperature.md)">IOCTL_THERMAL_READ_TEMPERATURE</a></p></td>
<td><p>The <a href="ioctl-thermal-read-temperature.md" data-raw-source="[IOCTL_THERMAL_READ_TEMPERATURE](ioctl-thermal-read-temperature.md)">IOCTL_THERMAL_READ_TEMPERATURE</a> I/O control request is sent by the ACPI driver to a temperature sensor driver. Upon receiving this request, the driver might be required to provide the temperature of the thermal zone.</p></td>
</tr>
</tbody>
</table>

 

 

 






