---
title: Role
description: Role
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e298d372-8af9-4552-a886-da1fe1a55ea0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Role


`Role` specifies whether the Terminal Services license server role is for a workgroup and a domain or for the entire enterprise.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that the Terminal Services license server role is for a workgroup and a domain. This is the default setting.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that the Terminal Services license server role is for the entire enterprise.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md) | **Role**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md).

## XML Example


The following XML output specifies that the Terminal Services license server role is for a workgroup and a domain.

```
<Role>0</Role>
```

## Related topics


[Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md)

 

 







