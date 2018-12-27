---
title: Low battery action
description: Specifies the action to take when the low batter level is reached.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9259D3B3-959A-46CE-821D-0D7CCAFF12C3


ms.date: 10/05/2017
ms.topic: article


---
# Low battery action

Specifies the action to take when the low batter level is reached.

## <span id="Aliases_and_setting_visibility"></span>Aliases and setting visibility

* **Windows Provisioning:** `LowAction`
* **PowerCfg:** `BATACTIONLOW`
* **GUID:** d8742dcb-3e6a-4b3c-b3fe-374623cdcf06
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
<td><p>No action is taken when the low battery level is reached.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Sleep</p></td>
<td><p>The system enters sleep when the low battery level is reached.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Hibernate</p></td>
<td><p>The system enters hibernate when the low battery level is reached.</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>Shut Down</p></td>
<td><p>The system shuts down when the low battery level is reached.</p></td>
</tr>
</tbody>
</table>

## <span id="Applies_to"></span>Applies to

Available in Windows Vista and later versions of Windows.
