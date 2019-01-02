---
title: CacheList
description: CacheList
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d136cb3c-0a3b-42b0-8c7d-4bd27c74235f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CacheList

`CacheList` configures Microsoft ReadyBoost™ flash storage devices that are used as supplemental memory caches. This is typically used for devices that have been integrated with the computer, such as an internal flash device or solid-state drive (SSD).

`CacheList` can contain up to eight [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) settings that represent a single ReadyBoost cache on the computer that you configure.

> [!Note]
> If more than eight [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) values are added, only the first eight caches, in the alphabetical order of their [CacheID](microsoft-windows-systemmaintenanceservice-cachelist-cache-cacheid.md), will be recognized.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | Specifies settings that represent a single ReadyBoost cache on the computer that you configure. |

## Parent Hierarchy

[Microsoft-Windows-SystemMaintenanceService](microsoft-windows-systemmaintenanceservice.md) | **CacheList**

## Valid Configuration Passes

specialize

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-SystemMaintenanceService](microsoft-windows-systemmaintenanceservice.md).

## XML Example

The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the primary hard drive is disk 0 (not shown in the XML), and the two ReadyBoost devices are Disk 1 and 2. On the first device, a 500-megabyte ReadyBoost cache is created, leaving the remainder of the device space for storage. The second device is entirely used by the ReadyBoost cache.

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

[Microsoft-Windows-SystemMaintenanceService](microsoft-windows-systemmaintenanceservice.md)
