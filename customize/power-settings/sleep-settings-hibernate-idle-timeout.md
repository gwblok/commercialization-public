---
title: Hibernate idle timeout
description: Specifies the duration of time after sleep that the system automatically wakes and enters hibernation.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5859EB3C-329F-4FF4-B512-5C1558A86BC2


ms.date: 10/05/2017
ms.topic: article


---

# Hibernate idle timeout


Specifies the duration of time after sleep that the system automatically wakes and enters hibernation.

This settings enables hibernate option on Modern Standby systems. Set the value to 0 to disable the feature.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `HibernateTimeout `

-   **PowerCfg:** `HIBERNATEIDLE   `

-   **GUID:** 9d7815a6-7ee4-497e-8888-515a05f02364

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


The value denotes the number of seconds.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum value</p></td>
<td><p>0 (Never idle to sleep)</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>Maximum integer</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
