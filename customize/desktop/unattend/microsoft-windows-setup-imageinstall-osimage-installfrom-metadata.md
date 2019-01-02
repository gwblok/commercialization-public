---
title: MetaData
description: MetaData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6609701e-b394-4702-ab52-5cbaeb9d4c67
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# MetaData

`MetaData` specifies a Windows edition or image in a Windows image (.wim) file.

Use the [Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md) and [Value](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-value.md) settings together to select a Windows edition or image based on the index, the name, or the description of the image.

Use the `DISM /Get-ImageInfo` command to determine which images and editions are included on your Windows DVD or Windows image (.wim) file. For instructions on how to select a Windows image using the `MetaData` setting, see the [Best Practices for Image Deployment](http://go.microsoft.com/fwlink/?LinkId=206672) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md) | Specifies whether the image number, name, or description is used to select the image in a .wim file. |
| [Value](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-value.md) | Specifies the value of the <code>Key</code> setting. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-osimage-installfrom.md) | **MetaData**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Examples

The following XML output shows how to configure the `ImageInstall` setting to install a specific Windows image from the Windows DVD by using the image index value:

```XML
<ImageInstall>
    <OSImage>
        <InstallFrom>
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>2</Value>
            </MetaData>
        </InstallFrom>
        <InstallTo>
            <DiskID>0</DiskID>
            <PartitionID>3</PartitionID>
        </InstallTo>
    </OSImage>
</ImageInstall>
```

The following XML output shows how to configure the `ImageInstall` setting to install a specific Windows image from a custom Windows image file (.wim) located on a network share. Windows Setup selects the image from the LaptopImages.wim file by referencing the image description of a fictional laptop model named "Model FNB1".

```XML
<ImageInstall>
    <OSImage>
        <InstallFrom>
            <Credentials>
                <Domain>FabrikamDomain</Domain>
                <Password>MyPassword</Password>
                <Username>MyUsername</Username>
            </Credentials>
            <Path>\\server\share\CustomWindowsImages\LaptopImages.wim</Path>
            <MetaData wcm:action="add">
                <Key>/IMAGE/DESCRIPTION</Key>
                <Value>Model FNB1</Value>
            </MetaData>
        </InstallFrom>
        <InstallTo>
            <DiskID>0</DiskID>
            <PartitionID>3</PartitionID>
        </InstallTo>
        <WillShowUI>OnError</WillShowUI>
        <InstallToAvailablePartition>false</InstallToAvailablePartition>
    </OSImage>
</ImageInstall>
```

## Related topics

[InstallFrom](microsoft-windows-setup-imageinstall-osimage-installfrom.md)

[Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md)

[Value](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-value.md)
