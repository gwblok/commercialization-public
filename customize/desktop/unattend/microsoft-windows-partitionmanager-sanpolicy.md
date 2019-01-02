---
title: SanPolicy
description: SanPolicy
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f7e00d87-a91b-4b6f-986a-94620d597fd5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SanPolicy


`SanPolicy` specifies the type of Storage Area Network (SAN) policy to apply to the computer. A SAN enables a server to mount disks and other storage devices automatically from other computers.

By configuring the SAN policy on a Windows image, you can control whether disks are automatically mounted, which disks can be mounted, and you can disable disks from being mounted automatically.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Mounts all available storage devices. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Mounts all storage devices except those on a shared bus.</p>
<p>Examples of shared buses are: SCSI, iSCSI, Fiber, and SAS.</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Does not mount storage devices.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-PartitionManager](microsoft-windows-partitionmanager.md) | **SanPolicy**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-PartitionManager](microsoft-windows-partitionmanager.md)

## XML Example


The following XML output shows how to configure the SAN policy to mount all available storage devices.

```
<SanPolicy>1</SanPolicy>
```

## Related topics


[Microsoft-Windows-PartitionManager](microsoft-windows-partitionmanager.md)

 

 







