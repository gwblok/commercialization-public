---
title: UninstallWindowsRE
description: UninstallWindowsRE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4118d371-d469-4d26-bb1a-a5540f31feb2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UninstallWindowsRE


`UninstallWindowsRE` specifies whether Windows Recovery Environment (Windows RE) is installed or removed from the system.

You can save hard disk space by configuring Windows Setup to uninstall Windows RE from the local hard disk.

**Warning**  
We recommend that you do not use this setting. Uninstalling Windows RE disables functionalities that allow users to troubleshoot and recover from startup problems.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>When Windows Setup completes, any default or OEM-specified Windows RE image is deleted from the local hard disk.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that when Windows Setup completes, any default or OEM-specified Windows RE image (including the default image) is installed on the local hard disk.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-WinRE-RecoveryAgent](microsoft-windows-winre-recoveryagent.md) | **UninstallWindowsRE**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-WinRE-RecoveryAgent](microsoft-windows-winre-recoveryagent.md).

## XML Example


The following XML output shows how to instruct Windows to save drive space by uninstalling any default or OEM-specified Windows RE image from the system.

```
<UninstallWindowsRE>true</UninstallWindowsRE>
```

## Related topics


[Microsoft-Windows-WinRE-RecoveryAgent](microsoft-windows-winre-recoveryagent.md)

 

 







