---
title: Extend
description: Extend
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ea9ad4b7-f3e1-4375-bf9c-3120d76b9389
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Extend


`Extend` specifies whether a newly-created primary partition is extended to fill the remainder of the hard disk.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the newly-created primary partition is extended to fill the remainder of the disk.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the newly-created partition is a fixed size, as specified by <code>CreatePartition:</code><a href="microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-size.md" data-raw-source="[Size](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-size.md)">Size</a>. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

When creating a new partition, you must either use `CreatePartition:`[Size](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-size.md), or set `CreatePartition:Extend` to true.

**Note**  
**To use extended and logical partitions:**

To create a logical partition that uses the remainder of the extended partition through Windows Setup, create a partition that has an initial fixed size. For example: `CreatePartition:Size=100`. Then, modify the partition by setting `ModifyPartition:Extend=true`.

Do not set both `CreatePartition:Extend` and `ModifyPartition:Extend` to **true**. For more information, see [How to Configure More Than Four Partitions on a BIOS-Based Hard Disk](http://go.microsoft.com/fwlink/?LinkId=214072).

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) | [CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md) | **Extend**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output for the `DiskConfiguration` setting shows how to create two partitions on a hard drive. The first partition has a fixed size of 100 megabytes (MB). The second partition is extended to fill the remainder of the hard disk.

```
<DiskConfiguration>

  <Disk wcm:action="add">
    <DiskID>0</DiskID> 
    <WillWipeDisk>true</WillWipeDisk> 
    <CreatePartitions>

      <!-- System partition -->
      <CreatePartition wcm:action="add">
        <Order>1</Order> 
        <Type>Primary</Type> 
        <Size>300</Size> 
      </CreatePartition>

      <!-- Windows partition -->
      <CreatePartition wcm:action="add">
        <Order>2</Order> 
        <Type>Primary</Type> 
        <Extend>true</Extend> 
      </CreatePartition>

    </CreatePartitions>
    <ModifyPartitions>

      <!-- System partition -->
      <ModifyPartition wcm:action="add">
        <Order>1</Order> 
        <PartitionID>1</PartitionID> 
        <Label>System</Label> 
        <Format>NTFS</Format> 
        <Active>true</Active> 
      </ModifyPartition>

      <!-- Windows partition -->
      <ModifyPartition wcm:action="add">
        <Order>2</Order> 
        <PartitionID>2</PartitionID> 
        <Label>Windows</Label> 
        <Letter>C</Letter> 
        <Format>NTFS</Format> 
      </ModifyPartition>
    </ModifyPartitions>
  </Disk>


  <WillShowUI>OnError</WillShowUI> 
</DiskConfiguration>


<ImageInstall>
  <OSImage>
    <InstallTo>
      <DiskID>0</DiskID> 
      <PartitionID>2</PartitionID> 
    </InstallTo>
  </OSImage>
</ImageInstall>
```

For full XML examples and recommended partition configurations, see [How to Configure UEFI/GPT-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214261) or [How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260).

## Related topics


[Extend](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-extend.md)

[CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md)

[How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260)

[How to Configure More Than Four Partitions on a BIOS-Based Hard Disk](http://go.microsoft.com/fwlink/?LinkId=214072)

 

 







