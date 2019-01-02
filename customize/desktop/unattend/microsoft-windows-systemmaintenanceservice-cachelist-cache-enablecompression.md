---
title: EnableCompression
description: EnableCompression
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 070202ea-8b9b-4c5f-8e29-46ab0c608af0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableCompression


`EnableCompression` specifies whether the Microsoft ReadyBoost™ cache uses compression.

Disabling compression can improve CPU usage and decrease battery consumption.

Enabling compression may be necessary for systems with a low amount of RAM or cache space, to ensure that the necessary pages can be stored.

-   For a portable computer with 1 gigabyte (GB) of RAM, we recommend using a fast internal flash device with a cache size of at least 4 GB, to avoid the need for cache compression.

-   For a portable computer with 2 GB or more of RAM, we recommend using a fast internal flash device with a cache size of at least 8 GB, to avoid the need for cache compression.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the ReadyBoost cache uses compression.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the ReadyBoost cache does not use compression.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | **EnableCompression**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md).

## XML Example


The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the first device does not use compression, while the second device uses compression.

```
<CacheList>
  <Cache>
    <CacheID>ReadyBoostCache1</CacheID>
    <DiskID>1</DiskID>
    <PartitionID>1</PartitionID>
    <CacheSizeMB>1024</CacheSizeMB>
    <EnableCompression>false</EnableCompression>
    <EnableEncryption>false</EnableEncryption>
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

 

 







