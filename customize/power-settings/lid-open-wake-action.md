---
title: Lid open wake action
description: Specifies the action to take when the system lid is opened.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 21BDC597-09AE-4AC0-9D78-64ED83DCE10E


ms.date: 10/05/2017
ms.topic: article


---

# Lid open wake action


Specifies the action to take when the system lid is opened.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `LidOpenWake       `

-   **PowerCfg:** `LIDOPENWAKE       `

-   **GUID:** 99ff10e7-23b1-4c07-a9d1-5c3206d741b4

-   **Hidden setting:** Yes

-   **Current AC power setting index:** 0x00000001

-   **Current DC power setting index:** 0x00000001

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
<td><p>No action is taken when the system lid is opened.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Turn on the display</p></td>
<td><p>The OS turns on the display when the system lid is opened.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows 10, version 1607 and later versions of Windows.

## <span id="related_topics"></span>Related topics


[LidNotificationsAreReliable](power-controls-lidnotificationsarereliable.md)
