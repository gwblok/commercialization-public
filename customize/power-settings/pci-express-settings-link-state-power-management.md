---
title: Link state power management
description: Specifies the personality of the power plan.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7239F601-A2EF-4B42-8D2E-DFC387C3F745


ms.date: 10/05/2017
ms.topic: article


---

# Link state power management


Specifies the personality of the power plan.

**Warning**  System administrators should not change the power plan personality settings.

 

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `ASPM`

-   **PowerCfg:** `ASPM`

-   **GUID:** ee12f906-d277-404b-b6da-e5fa1a576df5

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
<td><p>None</p></td>
<td><p>The power plan is a Power Saver plan.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Moderate Power Savings</p></td>
<td><p>The system attempts to use the L0 state when the link is idle.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Maximum Power Savings</p></td>
<td><p>The system attempts to use the L1 state when the link is idle.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
