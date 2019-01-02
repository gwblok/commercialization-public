---
title: InstallTo
description: InstallTo
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0c114602-099e-476d-971a-53cead3b51c0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# InstallTo

`InstallTo` specifies the disk and partition where you install the Windows operating system image.

You must specify valid values for the [DiskID](microsoft-windows-setup-imageinstall-osimage-installto-diskid.md) and [PartitionID](microsoft-windows-setup-imageinstall-osimage-installto-partitionid.md) settings. If you are installing to a blank disk, you must create and format partitions with the [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) and [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) settings.

## Comparison of OSImage Settings: InstallTo and InstallToAvailablePartition

For unattended installations, you must specify either the **InstallTo** or the [InstallToAvailablePartition](microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md) setting.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-Setup\ImageInstall\OSImage\InstallTo</p></td>
<td><p>Installs Windows to a specified disk and partition.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md" data-raw-source="[Microsoft-Windows-Setup\ImageInstall\OSImage\InstallToAvailablePartition](microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md)">Microsoft-Windows-Setup\ImageInstall\OSImage\InstallToAvailablePartition</a></p></td>
<td><p>Installs Windows to the first available partition that has enough space and does not already contain an installation of Windows.</p></td>
</tr>
</tbody>
</table>

> [!Note]
> In the **OSImage** setting, if you set the **InstallToAvailablePartition** setting to **true**, do not set the **InstallTo** setting.
> If both **InstallToAvailablePartition** and **InstallTo** are set the installation will fail.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DiskID](microsoft-windows-setup-imageinstall-osimage-installto-diskid.md) | Specifies the disk identifier of the hard disk on which to install Windows. |
| [PartitionID](microsoft-windows-setup-imageinstall-osimage-installto-partitionid.md) | Specifies the partition identifier of the partition on which to install Windows. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | InstallTo

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set the **ImageInstall** setting to install both an operating-system image and a data image.

```XML
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

[OSImage](microsoft-windows-setup-imageinstall-osimage.md)

[InstallToAvailablePartition](microsoft-windows-setup-imageinstall-osimage-installtoavailablepartition.md)
