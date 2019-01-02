---
title: SkipAutoActivation
description: SkipAutoActivation
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ca154db3-5742-4fbf-a424-b6033ee953cd
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SkipAutoActivation


`SkipAutoActivation` specifies whether Windows attempts to automatically activate. For automatic activation to complete, a valid Windows product key is required.

After Windows has been activated, it is not necessary to use the unattended-Setup setting: Microsoft-Windows-Security-SPP-UX\\`SkipAutoActivation`. Do not use the `SkipAutoActivation` setting on a system that has already been activated with a non-system locked pre-installation (SLP) license key.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that Windows does not attempt to automatically activate.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that Windows attempts to automatically activate. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Security-SPP-UX](microsoft-windows-security-spp-ux.md) | **SkipAutoActivation**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Security-SPP-UX](microsoft-windows-security-spp-ux.md).

## XML Example


The following sample XML output specifies that auto-activation is skipped.

```
<SkipAutoActivation>true</SkipAutoActivation>
```

## Related topics


[Microsoft-Windows-Security-SPP-UX](microsoft-windows-security-spp-ux.md)

[ProductKey](microsoft-windows-shell-setup-productkey.md)

[ProductKey](microsoft-windows-setup-userdata-productkey.md)

 

 







