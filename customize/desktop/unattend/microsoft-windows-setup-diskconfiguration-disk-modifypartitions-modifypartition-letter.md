---
title: Letter
description: Letter
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6627377a-9101-47b4-92d0-9c5dd8deb83d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Letter


`Letter` specifies a drive letter to assign to the partition.

**Note**  
Some partitions, such as system and recovery partitions, do not receive a drive letter by default. To set up files on these partitions, we recommend that you use the Windows Preinstallation Environment (Windows PE). In Windows PE, you can access and modify these partitions without affecting the way that the drive letters appear in Windows to the end user. For more information about system recovery, see the [Walkthrough: Deploy a System Recovery Image](http://go.microsoft.com/fwlink/?LinkId=206666) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference. For more information about Windows PE, see the [Windows Preinstallation Environment (Windows PE) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206667) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Drive_letter</em></p></td>
<td><p>Specifies the drive letter to apply to a partition. <em>Drive_letter</em> is an uppercase letter, C through Z.</p>
<p>If you do not specify a letter, this setting defaults to the first available letter from C through Z.</p>
<p><em>Drive_letter</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) | [ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md) | **Letter**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following example for the `DiskConfiguration` setting shows two partition modifications. The System and Recovery partitions do not receive a letter. The Windows partition receives the drive letter C. The Data partition receives the first available drive letter between D and Z, depending on what other drives and hardware are present on the computer.

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

      <!-- System partition -->
      <CreatePartition wcm:action="add">
        <Order>2</Order> 
        <Type>Primary</Type> 
        <Size>300</Size> 
      </CreatePartition>

      <!-- Windows partition -->
      <CreatePartition wcm:action="add">
        <Order>3</Order> 
        <Type>Primary</Type> 
        <Size>15000</Size> 
      </CreatePartition>

      <!-- Data partition -->
      <CreatePartition wcm:action="add">
        <Order>4</Order> 
        <Type>Primary</Type> 
        <Extend>true</Extend> 
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

      <!-- System partition -->
      <ModifyPartition wcm:action="add">
        <Order>2</Order> 
        <PartitionID>2</PartitionID> 
        <Label>System</Label> 
        <Format>NTFS</Format> 
        <Active>true</Active> 
      </ModifyPartition>

      <!-- Windows partition -->
      <ModifyPartition wcm:action="add">
        <Order>3</Order> 
        <PartitionID>3</PartitionID> 
        <Label>Windows</Label> 
        <Letter>C</Letter> 
        <Format>NTFS</Format> 
      </ModifyPartition>

      <!-- Data partition -->
      <ModifyPartition wcm:action="add">
        <Order>4</Order> 
        <PartitionID>4</PartitionID> 
        <Label>Data</Label> 
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
      <PartitionID>3</PartitionID> 
    </InstallTo>
  </OSImage>
</ImageInstall>
```

For full XML examples and recommended partition configurations, see [How to Configure UEFI/GPT-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214261) or [How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260).

## Related topics


[ModifyPartition](microsoft-windows-setup-diskconfiguration-disk-modifypartitions-modifypartition.md)

 

 







