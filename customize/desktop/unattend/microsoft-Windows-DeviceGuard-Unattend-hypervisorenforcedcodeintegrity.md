---
title: HypervisorEnforcedCodeIntegrity
description: Specifies the code integrity that will be enforced for the hypervisor, which is a layer of software under the OS that runs virtual machines.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: FE58E468-3E48-41EF-8F06-610707B829ED
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# HypervisorEnforcedCodeIntegrity

Specifies the code integrity that will be enforced for the hypervisor, which is a layer of software under the OS that runs virtual machines.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Code integrity for the hypervisor is not enabled.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Code integrity for the hypervisor is enabled.</p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy

[Microsoft-Windows-DeviceGuard-Unattend](microsoft-windows-deviceguard-unattend.md) | **HypervisorEnforcedCodeIntegrity**

## Valid Configuration Passes

offlineServicing

## Applies To

Windows 10 Enterprise

Windows Server 2016

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-DeviceGuard-Unattend](microsoft-windows-deviceguard-unattend.md).
