---
title: SignInMode
description: Use SignInMode to specify whether users switch to tablet mode by default after signing in.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8DB24A68-7F22-4863-9A32-294A52C7BE53
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SignInMode


Use `SignInMode` to specify whether users switch to tablet mode by default after signing in.

OEMs can configure this setting to support Continuum, which is a new, adaptive user experience in Windows 10 that optimizes the look and behavior of apps and the Windows UI for a given physical form factor and the customer's usage preferences. OEMs can also configure their devices to turn the hardware-based prompt on or off using [ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md). In addition, OEMs may also specify the device form factor by setting [DeviceForm](microsoft-windows-deployment-deviceform.md). For more information about Continuum, partners can download the "Windows 10 Continuum whitepaper" through the Microsoft Connect site.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Tablet mode</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Desktop</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Last used</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

offlineServicing

generalize

specialize

auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **SignInMode**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






