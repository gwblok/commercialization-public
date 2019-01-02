---
title: InstallToAvailablePartition
description: InstallToAvailablePartition
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a9f284f6-eb4c-4dde-9003-30ce86bade6b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# InstallToAvailablePartition


`InstallToAvailablePartition` specifies whether to install the Windows operating system to the first available partition that has enough space and does not already contain an installation of Windows.

If you are installing Windows to a blank disk, you must create and format partitions with the [CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md) and [ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md) settings, and set one of the partitions as the active partition. After the partitions are created and formatted, using the **InstallToAvailablePartition** setting will select the first available partition with enough space to install Windows.

## Comparison of OSImage Settings: InstallTo and InstallToAvailablePartition


For unattended installations, you must specify either the [InstallTo](microsoft-windows-setup-imageinstall-osimage-installto.md) setting or the **InstallToAvailablePartition** setting.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>microsoft-windows-setup-\ImageInstall\OSImage\InstallTo</p></td>
<td><p>Installs Windows to a specified disk and partition.</p></td>
</tr>
<tr class="even">
<td><p>microsoft-windows-setup-\ImageInstall\OSImage\InstallToAvailablePartition</p></td>
<td><p>Installs Windows to the first available partition that has enough space and does not already contain an installation of Windows.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
In the [OSImage](microsoft-windows-setup-imageinstall-osimage.md) setting, if you set the **InstallToAvailablePartition** setting to **true**, do not set the **InstallTo** setting.

If both **InstallToAvailablePartition** and **InstallTo** are set the installation will fail.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that Windows be installed to the first available partition with enough space.</p>
<p>Windows Setup searches for available partitions starting with disk 0 and partition 1 on the first disk and continuing through all available disks.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the Windows partition will be specified, by using the Unattend setting: microsoft-windows-setup-\ImageInstall\OSImage\InstallTo.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | InstallToAvailablePartition

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set the **InstallToAvailablePartition** setting.

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
        <InstallToAvailablePartition>true</InstallToAvailablePartition>
        <WillShowUI>OnError</WillShowUI>
    </OSImage>
</ImageInstall>
```

## Related topics


[OSImage](microsoft-windows-setup-imageinstall-osimage.md)

[InstallTo](microsoft-windows-setup-imageinstall-osimage-installto.md)

[CreatePartitions](microsoft-windows-setup-diskconfiguration-disk-createpartitions.md)

[ModifyPartitions](microsoft-windows-setup-diskconfiguration-disk-modifypartitions.md)

 

 







