---
title: EnableLUA
description: EnableLUA
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 85ac1c3e-eb4d-40e5-b7a1-12447203bc51
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableLUA


`EnableLUA` specifies whether Windows User Account Controls (UAC) notifies the user when programs try to make changes to the computer. UAC was formerly known as Limited User Account (LUA).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Windows notifies the user when programs try to make changes to the computer.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Windows does not notify the user when programs try to install software or make changes to the computer.</p>
<p>We do not recommend using this setting, but it can be selected for systems that use programs that are not certified for Windows 8, Windows Server 2012, Windows 7 or Windows Server 2008 R2 because they do not support UAC.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-LUA-Settings](microsoft-windows-lua-settings.md) | **EnableLUA**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-LUA-Settings](microsoft-windows-lua-settings.md).

## XML Example


The following XML output specifies that Windows does not notify the user when programs try to install software or make changes to the computer.

```
<EnableLUA>false</EnableLUA>
```

## Related topics


[Microsoft-Windows-LUA-Settings](microsoft-windows-lua-settings.md)

 

 







