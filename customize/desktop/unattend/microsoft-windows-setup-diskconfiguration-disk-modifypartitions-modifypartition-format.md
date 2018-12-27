---
title: Format
description: Format
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 480f29e2-5f4d-4249-a038-8fa214310d41
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Format


`Format` specifies whether to erase the partition, and which file system to apply to the partition.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>NTFS</strong></p></td>
<td><p>Formats the partition for the NTFS file system.</p>
<p>When CreatePartition<a href="microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md" data-raw-source="[Type](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md)">Type</a> is set to <strong>Primary</strong> or <strong>Logical</strong>, this is the default file format.</p></td>
</tr>
<tr class="even">
<td><p><strong>FAT32</strong></p></td>
<td><p>Formats the partition for the File Allocation Table (FAT) file system.</p>
<p>When CreatePartition<a href="microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md" data-raw-source="[Type](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md)">Type</a> is set to <strong>EFI</strong>, this is the default file format.</p></td>
</tr>
</tbody>
</table>

 

When CreatePartition\\[Type](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md) is set to **Extended** or **MSR**, the partition does not receive a file format.

When using a disk that already contains an existing partition structure, `Format` can be used to erase and reformat an existing partition. By default, if an existing partition structure is used, the existing partition is not erased or reformatted.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) | [ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md) | **Format**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Examples


The following XML output for the `DiskConfiguration` settings shows how to erase and reformat the second partition of a disk.

```
<DiskConfiguration>

  <Disk wcm:action="add">
    <DiskID>0</DiskID> 

      <ModifyPartition wcm:action="add">
        <Order>1</Order> 
        <PartitionID>2</PartitionID> 
        <Format>NTFS</Format> 
      </ModifyPartition>
    </ModifyPartitions>

</DiskConfiguration>
```

For full XML examples and recommended partition configurations, see [How to Configure UEFI/GPT-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214261) or [How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260).

## Related topics


[ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md)

 

 







