---
title: ModifyPartition
description: ModifyPartition
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4d07bc63-36b4-4a9e-a2b5-1de83a383bf2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ModifyPartition

`ModifyPartition` specifies a single partition on a disk to be modified

One or more `ModifyPartition` list items can exist in the [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) parent list.

The following table shows the modifications that can be made to various partition types.

| Partition Type        | Active    | Extend    | Format    | Letter    | Label    | TypeID    |
|:----------------------|:----------|:----------|:----------|:----------|:---------|:----------|
| **Primary**           | Yes       | Yes       | Yes       | Yes       | Yes      | Yes       |
| **Logical**           | No        | Yes       | Yes       | Yes       | Yes      | Yes       |
| **EFI System (ESP)**  | No        | No        | Yes       | Yes       | Yes      | No        |

> [!Note]
> **Microsoft Reserved (MSR)** and **Extended** partitions cannot be modified.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Active](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-active.md) | Specifies whether the partition is active. |
| [Extend](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-extend.md) | Specifies whether to extend the partition to use the remainder of the contiguous space on the hard disk. |
| [Format](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-format.md) | Specifies the file-system format to apply to the partition. |
| [Label](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-label.md) | Specifies the name to apply to the partition. |
| [Letter](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-letter.md) | Specifies the drive letter to assign to the partition. |
| [Order](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-order.md) | Specifies the order in which the partition will be modified. |
| [PartitionID](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-partitionid.md) | Specifies the identification number of the partition to modify. |
| [TypeID](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-typeid.md) | Specifies the hard drive partition type. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) | **ModifyPartition**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows two partition modifications. The first modification formats the partition for the NTFS file system, marks the partition as active, and labels it "System". The second modification formats the second partition on the disk to NTFS, labels it "Windows", and extends the partition to fill the remainder of the disk.

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
        <Size>350</Size> 
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

## Related topics

[ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md)
