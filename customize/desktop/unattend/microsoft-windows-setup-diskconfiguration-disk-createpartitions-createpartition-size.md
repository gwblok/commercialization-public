---
title: Size
description: Size
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1f473f22-38c9-40da-b870-5626d7bb8e72
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Size


`Size` specifies the size of the partition to create, in megabytes (MB).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>size_in_megabytes</em></p></td>
<td><p>Specifies the size of the partition that you create, in megabytes.</p>
<p>For example, to create a 2 gigabyte (GB) partition, set <code>Size</code> to 2000.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
Do not create a value for `Size` that entirely fills or exceeds the available space, because Windows reserves a small amount of space to manage partitions. For example, if you create an extended partition with 2000 MB, and you create two logical partitions with the size of 1000 MB each inside that partition, the second partition is not created. An error is logged, and installation is terminated.

-   To fill the available space on the drive with a primary partition, use the CreatePartition:[Extend](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-extend.md) setting. Do not set CreatePartition:`Size`.

-   To fill the available space on an extended partition with a logical partition, set CreatePartition:`Size` to a small value, such as **100**. Set ModifyPartition:[Extend](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition-extend.md) to **true**. Do not set CreatePartition:[Extend](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-extend.md). For more information, see [How to Configure More than Four Partitions on a BIOS-Based Hard Disk](http://go.microsoft.com/fwlink/?LinkId=214072).

-   Do not set both CreatePartition:`Size` and CreatePartition:[Extend](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-extend.md). If a value for `Size` is specified and CreatePartition:`Extend` is set to **true**, no partition is created. An error is logged, and installation is terminated.

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) | [CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md) | **Size**

## Applies To


For a list of supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


### Setting a Primary Partition to Fill the Available Space on a Drive

The following XML output for the `DiskConfiguration` setting shows how to create two partitions on a hard drive on a BIOS-based system. The first partition is 300 MB. The second partition extends to fill the remainder of the hard disk. 


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

### Setting a Logical Partition to Fill the Available Space in an Extended Partition

The following XML output for the `DiskConfiguration` setting shows how to create an extended partition that fills the remainder of the drive on a BIOS-based system. The extended partition includes two logical partitions. The first logical partition is 15 GB. The second logical partition extends to fill the remainder of the extended partition. 

```
<DiskConfiguration>

  <Disk wcm:action="add">
    <DiskID>0</DiskID> 
    <WillWipeDisk>true</WillWipeDisk> 
    <CreatePartitions>

      <!-- Recovery partition -->
      <CreatePartition wcm:action="add">
        <Order>1</Order> 
        <Type>Primary</Type> 
        <Size>3000</Size> 
      </CreatePartition>

      <!-- Utility2 partition -->
      <CreatePartition wcm:action="add">
        <Order>2</Order> 
        <Type>Primary</Type> 
        <Size>250</Size> 
      </CreatePartition>

      <!-- System partition -->
      <CreatePartition wcm:action="add">
        <Order>3</Order> 
        <Type>Primary</Type> 
        <Size>100</Size> 
      </CreatePartition>

      <!-- Extended partition -->
      <CreatePartition wcm:action="add">
        <Order>4</Order> 
        <Type>Extended</Type> 
        <Extend>true</Extend> 
      </CreatePartition>

      <!-- Windows partition -->
      <CreatePartition wcm:action="add">
        <Order>5</Order> 
        <Type>Logical</Type> 
        <Size>15000</Size> 
      </CreatePartition>

      <!-- Logical2 partition -->
      <CreatePartition wcm:action="add">
        <Order>6</Order> 
        <Type>Logical</Type> 
        <Size>100</Size> 
          <!-- Note: To create a logical partition that fills 
                     the rest of the extended partition, create the 
                     data partition with an initial size of 100 MB.
                     This will be changed in the ModifyPartition section. -->
      </CreatePartition>

    </CreatePartitions>
    <ModifyPartitions>

      <!-- Recovery partition -->
      <ModifyPartition wcm:action="add">
        <Order>1</Order> 
        <PartitionID>1</PartitionID> 
        <Label>Recovery</Label> 
        <Format>NTFS</Format> 
        <TypeID>0x27</TypeID>
      </ModifyPartition>

      <!-- Utility2 partition -->
      <ModifyPartition wcm:action="add">
        <Order>2</Order> 
        <PartitionID>2</PartitionID> 
        <Label>Utility2</Label> 
        <Letter>U</Letter> 
        <Format>NTFS</Format> 
        <TypeID>0x27</TypeID>
      </ModifyPartition>

      <!-- System partition -->
      <ModifyPartition wcm:action="add">
        <Order>3</Order> 
        <PartitionID>3</PartitionID> 
        <Label>System</Label>
        <Format>NTFS</Format> 
        <Active>true</Active> 
      </ModifyPartition>

      <!-- Extended partition:
           This partition does not need receive a partition number, 
           nor does it need to be modified -->

      <!-- Windows partition -->
      <ModifyPartition wcm:action="add">
        <Order>4</Order>
        <PartitionID>4</PartitionID> 
        <Label>Windows</Label> 
        <Letter>C</Letter> 
        <Format>NTFS</Format> 
      </ModifyPartition>

      <!-- Logical2 partition -->
      <ModifyPartition wcm:action="add">
        <Order>5</Order> 
        <PartitionID>5</PartitionID> 
        <Label>Logical2</Label> 
        <Letter>L</Letter> 
        <Format>NTFS</Format> 
        <Extend>true</Extend>
          <!-- Note: When modifying a logical partition, setting
                     "ModifyPartition|Extend=true" sets the partition to  
                     fill the remainder of the extended partition.
                     This overrides the "CreatePartition|Size" value. -->
      </ModifyPartition>

    </ModifyPartitions>
  </Disk>
  <WillShowUI>OnError</WillShowUI> 
</DiskConfiguration>


<ImageInstall>
  <OSImage>
    <InstallTo>
      <DiskID>0</DiskID> 
      <PartitionID>4</PartitionID> 
    </InstallTo>
  </OSImage>
</ImageInstall>
```

For full XML examples and recommended partition configurations, see [How to Configure UEFI/GPT-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214261) or [How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260).

## Related topics


[CreatePartition](microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition.md)

[How to Configure More than Four Partitions on a BIOS-Based Hard Disk](http://go.microsoft.com/fwlink/?LinkId=214072)

 

 







