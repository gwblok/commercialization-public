---
title: CreatePartitions
description: CreatePartitions
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c6a3e79e-d2ff-437c-899e-a11a937ea526
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CreatePartitions

`CreatePartitions` specifies one or more partitions to create on a hard disk. Partitions are created in the order specified by the [Order](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-order.md) setting.

If you are installing Windows to a blank hard disk, you must use the `CreatePartitions` and [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) settings to create and format partitions on the disk. You must also specify either the [InstallTo](microsoft-windows-setup-imageinstall-osimage-installto.md) or the [InstallToAvailablePartition](microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md) setting.

`CreatePartitions` settings can have one or more [CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md) list items, one for each partition to be configured.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md) | Specifies the order, size, and type of a single partition to be configured. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | **CreatePartitions**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output for the `DiskConfiguration` setting shows how to create two partitions on a hard drive on a BIOS-based system.

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

[Disk](microsoft-windows-setup-diskconfiguration-disk.md)
