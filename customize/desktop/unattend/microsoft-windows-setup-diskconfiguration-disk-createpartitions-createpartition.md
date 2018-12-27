---
title: CreatePartition
description: CreatePartition
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f7c47742-9a82-4888-8a8f-5a8bd9f3d4d8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CreatePartition

`CreatePartition` specifies a single partition to create on the hard disk.

If you are installing Windows to a blank hard disk, you must use `CreatePartition` and [ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md) to create and to format partitions on the disk. You must also add values to either [InstallTo](microsoft-windows-setup-imageinstall-osimage-installto.md) or [InstallToAvailablePartition](microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md) to specify where to install Windows.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Extend](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-extend.md) | Specifies whether to extend the partition to fill the disk. |
| [Order](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-order.md) | Specifies the creation order for multiple partitions. |
| [Size](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-size.md) | Specifies the size of the partition to create, in megabytes. |
| [Type](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type.md) | Specifies the type of partition to create. For example, you can specify a primary partition type or an extended partition type. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) | **CreatePartition**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output for the `DiskConfiguration` setting shows how to create a drive partition.

```XML
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

[CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md)
