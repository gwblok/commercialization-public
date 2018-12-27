---
title: PerfAutonomousMode
description: PerfAutonomousMode controls whether autonomous mode is enabled on systems that implement version 2 of the CPPC interface, and determines whether desired performance requests should be provided to the platform.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B3A2336E-2F8C-4580-B0CC-B805225C1202


ms.date: 10/05/2017
ms.topic: article


---

# PerfAutonomousMode


`PerfAutonomousMode` controls whether autonomous mode is enabled on systems that implement version 2 of the CPPC interface, and determines whether desired performance requests should be provided to the platform. On systems with other performance state interfaces, this setting has no effect.

**Note**  
Platforms that support CPPC version 2 may only support autonomous disabled or autonomous enabled mode. If only one mode is supported, the OS uses that mode and ignores the `PerfAutonomousMode` power setting.

 

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `PerfAutonomousMode`

-   **PowerCfg:** `PERFAUTONOMOUS`

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Index</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Disabled</p></td>
<td><p>The performance state engine disables autonomous mode, determines desired performance levels, and conveys those performance levels to the platform.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enabled</p></td>
<td><p>The performance state engine enables autonomous mode and stops providing desired performance levels to the platform.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


| Windows edition                                                        | x86-based devices | x64-based devices | ARM-based devices |
|------------------------------------------------------------------------|-------------------|-------------------|-------------------|
| Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) | x86               | amd64             | N/A               |
| Windows 10 Mobile                                                      | N/A               | N/A               | Supported         |
