---
title: DiskID
description: DiskID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f67bb944-a424-461e-abd5-31d3871e51ef
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DiskID


`DiskID` specifies the identification number of the disk on which to install a data image.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Disk_identification_number</em></p></td>
<td><p>Specifies the identification number of the disk on which to install a data image. <em>Disk_identification_number</em> is an integer.</p>
<p>Disk IDs start with 0. For example, to specify the first disk, assign <code>DiskID</code> to <strong>0</strong>. For the second disk, assign <code>DiskID</code> to <strong>1</strong>.</p>
<p>If you are installing a data image to a computer with a single disk, assign <code>DiskID</code> to <strong>0</strong>. In contrast, <a href="microsoft-windows-setup-imageinstall-dataimage-installto-partitionid.md" data-raw-source="[PartitionID](microsoft-windows-setup-imageinstall-dataimage-installto-partitionid.md)">PartitionID</a> starts with <strong>1</strong> for the first partition.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | [InstallTo](microsoft-windows-setup-imageinstall-dataimage-installto.md) | **DiskID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set the `ImageInstall` setting if you are installing a data image.

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

 

 







