---
title: HideOnlineAccountScreens
description: HideOnlineAccountScreens
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 34787d16-db5d-4844-9440-89734ab8cceb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HideOnlineAccountScreens


`HideOnlineAccountScreens` specifies whether the user will be required to sign-in during OOBE. This setting is primarily for enterprises that do not want employees using email addresses as user names.

For the sign-in page to appear, the user must have an internet connection.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Hides the sign-in page during OOBE.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not hide the sign-in page during OOBE.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **HideOnlineAccountScreens**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to hide the sign-in page during OOBE.

```
<OOBE>
     <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
