---
title: HideOEMRegistrationScreen
description: HideOEMRegistrationScreen
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b68056c6-ad85-40d1-be79-afd27a150fb7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HideOEMRegistrationScreen


`HideOEMRegistrationScreen` specifies whether the OEM registration page appears during OOBE. If this setting exists, the page will not appear during OOBE, regardless of the oobe.xml values.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Hides the OEM registration page during OOBE.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not hide the OEM registration page during OOBE.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **HideOEMRegistrationScreen**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to hide the OEM registration page during OOBE.

```
<OOBE>
     <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
