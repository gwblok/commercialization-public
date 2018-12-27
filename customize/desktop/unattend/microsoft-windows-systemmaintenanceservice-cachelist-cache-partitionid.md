---
title: PartitionID
description: PartitionID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cdc57e97-8dd8-4782-95ef-8122c2c6a8bb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PartitionID


`PartitionID` specifies the Partition ID that identifies the Microsoft ReadyBoost™ device. This value is used with [DiskID](microsoft-windows-systemmaintenanceservice-cachelist-cache-diskid.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the partition ID of the ReadyBoost device.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | **PartitionID**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md).

## XML Example


The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the primary hard drive is disk 0 (which is not listed in the XML example), and the two ReadyBoost devices are on Disk 1, Partition 1, and Disk 2, Partition 1.

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


[DiskID](microsoft-windows-systemmaintenanceservice-cachelist-cache-diskid.md)

[Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md)

 

 







