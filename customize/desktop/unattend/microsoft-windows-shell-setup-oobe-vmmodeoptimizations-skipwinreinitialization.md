---
title: SkipWinREInitialization
description: Use SkipWinREInitialization in VM mode, particularly in a container scenario where recovery is not important, to skip initialization of the Windows Recovery Environment (Windows RE) image.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: C154A10C-609C-4385-A065-FDBFDA1645B2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SkipWinREInitialization


Use `SkipWinREInitialization` in VM mode, particularly in a container scenario where recovery is not important, to skip initialization of the Windows Recovery Environment (Windows RE) image.

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
<td><p>Does not skip initialization of the Windows RE image when in VM mode.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>true</p></td>
<td><p>Skips initialization of the Windows RE image when in VM mode.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | [VMModeOptimizations](microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md) | **SkipWinREInitialization**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






