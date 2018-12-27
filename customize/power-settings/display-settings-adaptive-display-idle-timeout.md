---
title: Adaptive display idle timeout
description: Specifies whether the OS automatically scales the display idle time-out based on user activity.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 96EAD755-36EB-419E-8669-C566C26AA2A4


ms.date: 10/05/2017
ms.topic: article


---

# Adaptive display idle timeout


Specifies whether the OS automatically scales the display idle time-out based on user activity.

If the user provides input to the system shortly after the display idle timeout is reached, Windows automatically extends the display idle time-out to deliver a better user experience.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `AdaptiveTimeout `

-   **PowerCfg:** `VIDEOADAPT `

-   **GUID:** 90959d22-d6a1-49b9-af93-bce885ad335b

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
<td><p>Windows does not adaptively extend the display idle timeout.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enabled</p></td>
<td><p>Windows adaptively extends the display idle timeout.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
