---
title: EnableEncryption
description: EnableEncryption
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a7467cfb-a75f-403c-82e7-001abe487cfb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableEncryption


`EnableEncryption` specifies whether the Microsoft ReadyBoost™ cache uses encryption.

Enabling encryption can improve system security, especially on a shared computer.

Disabling encryption can improve system performance and decrease battery consumption.

This setting affects only internal (non-removable) devices. External devices are automatically configured with encryption to prevent data theft from a lost or stolen device.

**Note**  
Administrators can use Group Policy to ensure ReadyBoost devices are encrypted. For more information, see the MSDN topic: [Group Policy](http://go.microsoft.com/fwlink/?LinkId=143404).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the ReadyBoost cache uses encryption.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the ReadyBoost cache does not use encryption.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md) | [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | [Cache](microsoft-windows-systemmaintenanceservice-cachelist-cache.md) | **EnableEncryption**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-systemmaintenanceservice-](microsoft-windows-systemmaintenanceservice.md).

## XML Example


The following XML output example shows a configuration of two ReadyBoost devices. On this sample system, the first device does not use encryption, while the second device uses encryption.

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

 

 







