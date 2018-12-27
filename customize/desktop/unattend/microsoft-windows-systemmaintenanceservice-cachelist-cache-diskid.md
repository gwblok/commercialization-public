---
title: DiskID
description: DiskID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f2b71dd3-cd71-403a-a9c3-4bc4faa6349b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DiskID


`DiskID` specifies the Disk ID that identifies the Microsoft ReadyBoost™ device. This value is used with [PartitionID](microsoft-windows-systemmaintenanceservice-cachelist-cache-partitionid.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the disk ID of the ReadyBoost device.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | **DiskID**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md).

## XML Example


The following example XML output shows a configuration of two ReadyBoost devices. On this sample system, the primary hard drive is disk 0 (which is not listed in the XML example), and the two ReadyBoost devices are on Disk 1, Partition 1, and Disk 2, Partition 1.

```
<CacheList>
  <Cache>
    <CacheID>ReadyBoostCache1</CacheID>
    <DiskID>1</DiskID>
    <PartitionID>1</PartitionID>
    <CacheSizeMB>1024</CacheSizeMB>
    <EnableCompression>false</EnableCompression>
    <EnableEncryption>true</EnableEncryption>
  </Cache>
  <Cache>
    <CacheID>ReadyBoostCache2</CacheID>
    <DiskID>2</DiskID>
    <PartitionID>1</PartitionID>
    <EnableCompression>true</EnableCompression>
    <EnableEncryption>true</EnableEncryption>
  </Cache>
</CacheList>
```

## Related topics


[PartitionID](microsoft-windows-systemmaintenanceservice-cachelist-cache-partitionid.md)

[Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md)

 

 







