---
title: SkipNotifyUILanguageChange
description: Use SkipNotifyUILanguageChange in VM mode if the language will not change during setup.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B5B9CD2C-91F1-47B7-A185-D65B3C92C1DE
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SkipNotifyUILanguageChange


Use `SkipNotifyUILanguageChange` in VM mode if the language will not change during setup.

**Note**  You must specify /mode:vm during sysprep to fully enable this setting.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>false</p></td>
<td><p>The OS informs OOBE to run the language change OOBE plugin.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>true</p></td>
<td><p>The OS informs OOBE to skip running the language change OOBE plugin.</p>
<p>When the plugin is not run, components that register for UI language change notifications will not have their callbacks invoked during OOBE.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | [VMModeOptimizations](microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md) | **SkipNotifyUILanguageChange**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






