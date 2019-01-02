---
title: Windows power and battery subsystem requirements
description: This section describes the user experience requirements for the power and battery charging subsystem in a hardware platform that runs Windows.
MS-HAID:
- 'cstandby.windows\_power\_and\_battery\_subsystem\_requirements'
- 'p\_weg\_hardware.windows\_power\_and\_battery\_subsystem\_requirements'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 178037E0-71E1-4A58-8441-A723881AFAEE

ms.date: 05/02/2017
ms.topic: article


---

# Windows power and battery subsystem requirements


To meet user expectations and provide a quality experience, all Windows PCs must have consistent behavior for battery charging and system power transitions. Starting with Windows 8 and Windows 8.1, this design principle extends to battery-powered hardware platforms that are based on System on a Chip (SoC) integrated circuits and that support the modern standby power model.

This section describes the user experience requirements for the power and battery charging subsystem in a hardware platform that runs Windows. It provides detailed implementation guidance for platform designers and firmware developers. They can use this information to ensure their platforms are compatible with Windows power management software.

The information in this section pertains to all processor architectures—x86, x64, and ARM—that are supported by Windows. In addition, this information applies both to low-power platforms that implement the modern standby power model and to platforms that support the traditional ACPI sleep (S3) and hibernate (S4) power states.

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
<td><p><a href="user-experience-principles-for-battery-charging.md" data-raw-source="[User experience principles for battery charging](user-experience-principles-for-battery-charging.md)">User experience principles for battery charging</a></p></td>
<td><p>Outlines the five fundamental user experience principles for battery charging.</p></td>
</tr>
<tr class="even">
<td><p><a href="power-and-charging-subsystem-implementation.md" data-raw-source="[Power and charging subsystem implementation](power-and-charging-subsystem-implementation.md)">Power and charging subsystem implementation</a></p></td>
<td><p>Describes how to implement the battery power and charging subsystem on a Windows platform.</p></td>
</tr>
<tr class="odd">
<td><p><a href="acpi-battery-and-power-subsystem-firmware-implementation.md" data-raw-source="[ACPI battery and power subsystem firmware implementation](acpi-battery-and-power-subsystem-firmware-implementation.md)">ACPI battery and power subsystem firmware implementation</a></p></td>
<td><p>This topic details how the platform should expose power subsystem information to the Windows power manager.</p></td>
</tr>
<tr class="even">
<td><p><a href="battery-and-power-subsystem-hardware-design.md" data-raw-source="[Battery and power subsystem hardware design](battery-and-power-subsystem-hardware-design.md)">Battery and power subsystem hardware design</a></p></td>
<td><p>Explains the many factors in designing the battery and power subsystem hardware.</p></td>
</tr>
<tr class="odd">
<td><p><a href="platform-requirements-and-motivation.md" data-raw-source="[Platform requirements and motivation](platform-requirements-and-motivation.md)">Platform requirements and motivation</a></p></td>
<td><p>Describes the hardware requirements and motivation for the power and battery subsystem on the Windows platform.</p></td>
</tr>
<tr class="even">
<td><p><a href="power-and-battery-subsystem-checklist.md" data-raw-source="[Power and battery subsystem checklist](power-and-battery-subsystem-checklist.md)">Power and battery subsystem checklist</a></p></td>
<td><p>System designers can use the checklists included in this section to verify that their platform designs and system firmware follow the Windows guidelines for power and battery subsystem operation.</p></td>
</tr>
</tbody>
</table>

 

 

 






