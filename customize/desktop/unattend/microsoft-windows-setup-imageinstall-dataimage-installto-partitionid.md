---
title: PartitionID
description: PartitionID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 01bf5811-296b-4644-8d6b-a45a6ea87b3b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PartitionID


`PartitionID` specifies the identification number of the partition on which to install a data image. Partition indexes are relative 1-based. The first partition on a disk has the value of 1, the second, 2, and so on.

**Note**  
Only primary and logical partitions are used to define the partition ID. Extended partitions are ignored.

 

For example:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Primary (1)</p></td>
<td><p>Extended</p></td>
<td><p>Primary (2)</p></td>
<td><p>Primary (3)</p></td>
</tr>
</tbody>
</table>

 

Because the partition structure on a disk can change during installation, it is important to be aware of the changes to the partitions on a disk as you are creating your unattended installation answer file.

If you create additional partitions during Windows Setup, `PartitionID` must exactly match the partition that you want to modify. For example, if you add two logical partitions to your disk configuration and then want to modify the last partition, the partition ID of the last partition will have changed from 3 to 5:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Primary (1)</p></td>
<td><p>Extended</p>
<p>Logical (2)</p>
<p>Logical (3)</p></td>
<td><p>Primary (4)</p></td>
<td><p>Primary (5)</p></td>
</tr>
</tbody>
</table>

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Partition_identification_number</em></p></td>
<td><p>Specifies the identification number of the partition on which to install a data image. <em>Partition_identification_number</em> is an integer.</p>
<p>Partition numbering starts with 1 and includes primary and logical partitions but not extended partitions. By default, the first partition on a disk has the value of 1, the second, 2, and so on. If an extended partition is created before a primary partition and then modified to include several logical partitions, this value for primary partitions created later than the extended partition can change, unless these values are set explicitly.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | [InstallTo](microsoft-windows-setup-imageinstall-dataimage-installto.md) | **PartitionID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set the `ImageInstall` setting to install both an operating system image and a data image.

```
<ImageInstall>
    <OSImage>
        <InstallFrom>
            <Credentials>
                <Domain>FabrikamDomain</Domain>
                <Password>MyPassword</Password>
                <Username>MyUsername</Username>
            </Credentials>
            <Path>\\networkshare\share\install.wim</Path>
            <MetaData wcm:action="add">
                <Key>/IMAGE/NAME</Key>
                <Value>FabrikamCustomOSImage</Value>
            </MetaData>
        </InstallFrom>
        <InstallTo>
            <DiskID>0</DiskID>
            <PartitionID>1</PartitionID>
        </InstallTo>
        <WillShowUI>OnError</WillShowUI>
        <InstallToAvailablePartition>false</InstallToAvailablePartition>
    </OSImage>
    <DataImage wcm:action="add">
        <InstallTo>
            <DiskID>0</DiskID>
            <PartitionID>2</PartitionID>
        </InstallTo>
        <InstallFrom>
            <Credentials>
                <Domain>FabrikamDomain</Domain>
                <Password>MyPassword</Password>
                <Username>MyUsername</Username>
            </Credentials>
            <Path>\\networkshare\share\data.wim</Path>
            <MetaData wcm:action="add">
                <Key>/IMAGE/NAME</Key>
                <Value>FabrikamData</Value>
            </MetaData>
        </InstallFrom>
        <Order>1</Order>
    </DataImage>
</ImageInstall>
```

## Related topics


[InstallTo](microsoft-windows-setup-imageinstall-dataimage-installto.md)

 

 







