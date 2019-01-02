---
title: Cache
description: Cache
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b620476f-db73-442c-ada6-74aceb5fa8cb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Cache

`Cache` specifies settings for a Microsoft ReadyBoost™ flash-storage cache, to be used as a supplemental memory cache. This is typically used for devices that have been integrated with the computer, such as an internal flash device or solid-state drive (SSD).

## Values

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CacheID](microsoft-windows-systemmaintenanceservice-cachelist-cache-cacheid.md) | Specifies a unique cache ID. |
| [CacheSizeMB](microsoft-windows-systemmaintenanceservice-cachelist-cache-cachesizemb.md) | Specifies the size of the ReadyBoost cache in megabytes (MB). |
| [DiskID](microsoft-windows-systemmaintenanceservice-cachelist-cache-diskid.md) | Specifies the Disk ID that identifies the ReadyBoost device. Used with [PartitionID](microsoft-windows-systemmaintenanceservice-cachelist-cache-partitionid.md). |
| [EnableCompression](microsoft-windows-systemmaintenanceservice-cachelist-cache-enablecompression.md) | Specifies whether the ReadyBoost cache uses compression. |
| [EnableEncryption](microsoft-windows-systemmaintenanceservice-cachelist-cache-enableencryption.md) | Specifies whether the ReadyBoost cache uses encryption. |
| [PartitionID](microsoft-windows-systemmaintenanceservice-cachelist-cache-partitionid.md) | Specifies the Partition ID that identifies the ReadyBoost device. Used with [DiskID](microsoft-windows-systemmaintenanceservice-cachelist-cache-diskid.md). |

## Parent Hierarchy

[Microsoft-Windows-SystemMaintenanceService](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | **Cache**

## Valid Configuration Passes

specialize

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SystemMaintenanceService](microsoft-windows-systemmaintenanceservice.md).

## XML Example

The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the primary hard drive is disk 0 (not shown in the XML example), and the two ReadyBoost devices are Disk 1 and 2. On the first device, a 500-megabyte ReadyBoost cache is created, leaving the remainder of the device space for storage. The second device is entirely used by the ReadyBoost cache.

```XML
<CacheList>
  <Cache>
    <CacheID>ReadyBoostCache1</CacheID>
    <DiskID>1</DiskID>
    <PartitionID>1</PartitionID>
    <CacheSizeMB>500</CacheSizeMB>
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

[CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md)
