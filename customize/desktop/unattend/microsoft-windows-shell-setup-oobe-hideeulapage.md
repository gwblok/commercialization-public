---
title: HideEULAPage
description: HideEULAPage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3ea2f306-f380-4416-9c5c-5c2b452bec5d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# HideEULAPage

`HideEULAPage` specifies whether to hide the Microsoft Software License Terms page of Windows Welcome.

> [!Note]
> OEMs and System Builders can only use this setting for testing prior to shipment.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the Microsoft Software License Terms page of Windows Welcome is not displayed.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the Microsoft Software License Terms page of Windows Welcome is displayed.</p>
<p>This is the default value.</p>
<div class="alert">
<strong>Note</strong><br/><p>If the Microsoft Software License Terms have already been accepted, this page does not appear.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **HideEULAPage**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to hide the EULA page during Windows Welcome.

```
<OOBE>
   <HideEULAPage>true</HideEULAPage>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)

