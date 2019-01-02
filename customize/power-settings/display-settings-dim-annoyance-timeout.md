---
title: Dim annoyance timeout
description: This setting denotes the user annoyance detection threshold. It specifies the duration between automatic display brightness level reduction and user input to consider the automatic display brightness level reduction as an annoyance to the user.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: A1FFA0F1-6A6D-4AD2-BECD-E21C9F8F19E3


ms.date: 10/05/2017
ms.topic: article


---

# Dim annoyance timeout


This setting denotes the user annoyance detection threshold. It specifies the duration between automatic display brightness level reduction and user input to consider the automatic display brightness level reduction as an annoyance to the user.

This setting applies only to portable computers that support Windows control of the brightness level of an integrated display device. In most situations, you should not change the default value of this setting.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `AdapativeIncrease     `

-   **PowerCfg:** `VIDEOADAPTINC       `

-   **GUID:** 82dbcf2d-cd67-40c5-bfdc-9f1a5ccd4663

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
<td><p>0 (Do not detect user annoyance.)</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>Maximum integer</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows 7 and later versions of Windows.
