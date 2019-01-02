---
title: Prompt for password on resume
description: Specifies whether the user must enter a password at the secure desktop when the system resumes from sleep.Note  All Windows desktop editions have this setting enabled by default.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 17EAB92F-0780-4540-A2CA-37E274FB9935


ms.date: 10/05/2017
ms.topic: article


---

# Prompt for password on resume


Specifies whether the user must enter a password at the secure desktop when the system resumes from sleep.

**Note**  All Windows desktop editions have this setting enabled by default. This is a change from Windows 8.1 and earlier which had the setting disabled by default on some editions.

 

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `LockConsoleOnWake     `

-   **PowerCfg:** `CONSOLELOCK     `

-   **GUID:** 0e796bdb-100d-47d6-a2d5-f7d2daa51f51

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
<td><p>The system returns to the desktop when resuming from sleep.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enabled</p></td>
<td><p>The system returns to the secure desktop, and the user must enter a password when the system resumes from sleep.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
