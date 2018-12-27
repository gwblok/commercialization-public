---
title: Lid switch close action
description: Specifies the action to take when the system lid is closed.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1208091E-584E-4F6D-A53A-3348EAC1016B


ms.date: 10/05/2017
ms.topic: article


---

# Lid switch close action


Specifies the action to take when the system lid is closed.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `LidAction       `

-   **PowerCfg:** `LIDACTION       `

-   **GUID:** 5ca83367-6e45-459f-a27b-476b1d01c936

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
<td><p>Do Nothing</p></td>
<td><p>No action is taken when the system lid is closed.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Sleep</p></td>
<td><p>The system enters sleep when the system lid is closed.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Hibernate</p></td>
<td><p>The system enters hibernate when the system lid is closed.</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>Shut Down</p></td>
<td><p>The system shuts down when the system lid is closed.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
