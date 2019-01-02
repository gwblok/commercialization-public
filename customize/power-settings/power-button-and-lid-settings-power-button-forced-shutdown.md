---
title: Power button forced shutdown
description: Specifies the type of system shutdown that occurs when the system power button is pressed if the power button action is set to Shut Down.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2FDF2D94-9910-4756-9804-9CAFF1573A6A


ms.date: 10/05/2017
ms.topic: article


---

# Power button forced shutdown


Specifies the type of system shutdown that occurs when the system power button is pressed if the [power button action](power-button-and-lid-settings-power-button-action.md) is set to Shut Down.

**Warning**  If you enable this setting and a user presses the power button to shut down the system, any open documents might not be saved and data loss could occur.

 

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `ForcedShutdown `

-   **PowerCfg:** `SHUTDOWN `

-   **GUID:** 833a6b62-dfa4-46d1-82f8-e09e34d029d6

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
<td><p>Off</p></td>
<td><p>A normal system shutdown will occur.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>On</p></td>
<td><p>A forced system shutdown will occur.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows 7 and later versions of Windows.
