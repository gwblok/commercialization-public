---
title: HideWirelessSetupInOOBE
description: HideWirelessSetupInOOBE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ea9e9257-3335-47af-a224-60964eb79c1c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HideWirelessSetupInOOBE


`HideWirelessSetupInOOBE` specifies whether to hide the **Join Wireless Network** screen that appears during Windows Welcome.

During Windows Welcome, the **Join Wireless Network** screen prompts the end user to connect to a wireless network when all of the following conditions are met:

-   `HideWirelessSetupInOOBE` is not set to **true**.

-   The computer has a wireless network device.

-   The drivers for the wireless network device are available and installed.

-   A wireless network is available and detected.

-   A connection to a wireless network has not already been established in a previous Windows installation on the same computer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Hides the <strong>Join Wireless Network</strong> screen during Windows Welcome.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not hide the <strong>Join Wireless Network</strong> screen during Windows Welcome.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **HideWirelessSetupInOOBE**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to set Windows Welcome to always hide the **Join Wireless Network** screen.

```
<OOBE>
  <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
</OOBE>
```

## Related topics
[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)

 

 







