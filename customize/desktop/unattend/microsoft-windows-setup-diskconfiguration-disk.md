---
title: Disk
description: Disk
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d4b94e3c-1ff8-4422-b607-c4bbff21dd37
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Disk

`Disk` specifies the disk settings to add or to edit on the destination computer. `Disk` is a list item type, and each instance of `Disk` in an unattended installation answer file applies to a single hard disk (specified by [DiskID](microsoft-windows-setup-diskconfiguration-disk-diskid.md)).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) | Specifies a list of [CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md) items. |
| [DiskID](microsoft-windows-setup-diskconfiguration-disk-diskid.md) | Specifies the identification number of the disk to edit. |
| [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) | Specifies a list of [ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md) items. |
| [WillWipeDisk](microsoft-windows-setup-diskconfiguration-disk-willwipedisk.md) | Specifies whether to reformat the disk. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | **Disk**

## Applies To

For a list of supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Examples

### BIOS-Based System with Two Hard Drives

The following XML output for the `DiskConfiguration` setting shows partition modifications for a BIOS-based computer with two hard drives.

```XML
<DiskConfiguration>

  <!-- First hard drive -->
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

  <!-- Second hard drive -->
  <Disk wcm:action="add">
    <DiskID>1</DiskID> 
    <WillWipeDisk>true</WillWipeDisk> 
    <CreatePartitions>

      <!-- Data partition -->
      <CreatePartition wcm:action="add">
        <Order>1</Order> 
        <Type>Primary</Type> 
        <Extend>true</Extend> 
      </CreatePartition>

    </CreatePartitions>
    <ModifyPartitions>

      <!-- Data partition -->
      <ModifyPartition wcm:action="add">
        <Order>1</Order> 
        <PartitionID>1</PartitionID> 
        <Label>Data</Label> 
        <Letter>D</Letter> 
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

[DiskConfiguration](microsoft-windows-setup-diskconfiguration.md)
