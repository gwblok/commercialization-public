---
title: SkipAdministratorProfileRemoval
description: Use SkipAdministratorProfileRemoval to skip removal of the administrator profile when in VM mode.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: C4CD25BC-A012-4237-B5AD-F62ED5F654F5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SkipAdministratorProfileRemoval


Use `SkipAdministratorProfileRemoval` to skip removal of the administrator profile when in VM mode.

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
<td><p>Does not skip removal of the administrator profile when in VM mode.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>true</p></td>
<td><p>Skips removal of the administrator profile when in VM mode.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | [VMModeOptimizations](microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md) | **SkipAdministratorProfileRemoval**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






