---
title: Allow sleep with open remote files
description: Configures the network file system to prevent the computer from automatically entering sleep when remote network files are open.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 423B6B50-E1FD-43FA-B36E-DF74C353541B


ms.date: 10/05/2017
ms.topic: article


---

# Allow sleep with open remote files


Configures the network file system to prevent the computer from automatically entering sleep when remote network files are open.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `AllowRemoteOpenSleep`

-   **PowerCfg:** `ALLOWREMOTEOPENSLEEP`

-   **GUID:** d4c1d4c8-d5cc-43d3-b83e-fc51215cb04d

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
<td><p>Prevents automatic sleep when remote network files are open. However, if the open files are stored in Offline Files and are backed by the Offline File cache, automatic sleep is allowed.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>On</p></td>
<td><p>Prevents automatic sleep when remote network files are open. However, if the open files are stored in Offline Files or the open files have not been updated since they were originally opened, automatic sleep is allowed.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
