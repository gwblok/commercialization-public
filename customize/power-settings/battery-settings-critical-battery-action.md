---
title: Critical battery action
description: Specifies the action to take when the critical batter level is reached.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: BE25274D-672B-46ED-B69E-DF30297B971B


ms.date: 10/05/2017
ms.topic: article


---
# Critical battery action

Specifies the action to take when the critical batter level is reached.

## <span id="Aliases_and_setting_visibility"></span>Aliases and setting visibility

* **Windows Provisioning:** `CriticalAction`
* **PowerCfg:** `BATACTIONCRIT`
* **GUID:** 637ea02f-bbcb-4015-8e2c-a1c7b9c0b546
* **Hidden setting:** Yes

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
<td><p>Do Nothing</p></td>
<td><p>No action is taken when the critical battery level is reached.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Sleep</p></td>
<td><p>The system enters sleep when the critical battery level is reached.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Hibernate</p></td>
<td><p>The system enters hibernate when the critical battery level is reached.</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>Shut Down</p></td>
<td><p>The system shuts down when the critical battery level is reached.</p></td>
</tr>
</tbody>
</table>

## <span id="Applies_to"></span>Applies to

Available in Windows Vista and later versions of Windows.
