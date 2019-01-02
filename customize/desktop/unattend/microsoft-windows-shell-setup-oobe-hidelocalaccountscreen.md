---
title: HideLocalAccountScreen
description: HideLocalAccountScreen
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: eac0c5c7-689c-4bb8-90bf-902ae8e08f39
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HideLocalAccountScreen


`HideLocalAccountScreen` specifies whether end users must set the Administrator password screen that appears during OOBE.

This setting applies only to the Windows Server editions.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Hides the Administrator password screen during OOBE.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not hide the Administrator password screen during OOBE.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **HideLocalAccountScreen**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to hide the Administrator password screen during OOBE.

```
<OOBE>
     <HideLocalAccountScreen>true</HideLocalAccountScreen>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
