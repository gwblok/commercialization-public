---
title: CacheSizeMB
description: CacheSizeMB
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: adab85d0-7e97-4d6c-842e-bf7a5c3ad9ad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CacheSizeMB


`CacheSizeMB` specifies the size of the Microsoft ReadyBoost™ cache, in megabytes (MB).

**Note**  
The maximum cache size on a device partition formatted as FAT32 is 4096 MB, which is equal to 4 gigabytes (GB). To use a larger cache size, use a partition formatted as NTFS or exFAT. For information about reformatting a partition using NTFS, see [Format](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-format.md).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Size</em></p></td>
<td><p>Specifies the size of the ReadyBoost cache, in megabytes. <em>Size</em> is an integer value between 230 and 32768, so the range is from 230 MB to 32 GB.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-systemmaintenanceservice](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | **CacheSizeMB**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md).

## XML Example


The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the first device includes a cache size of 1 GB. On the second device, the cache is configured to fill the entire device.

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


[Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md)

 

 







