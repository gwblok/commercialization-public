---
title: ImageInstall
description: ImageInstall
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bbf815c5-9107-44c8-bc08-ec1aef071f21
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ImageInstall

`ImageInstall` specifies the Windows image or secondary data image to install and the location to which the image is to be installed.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | Specifies the secondary data image to install. |
| [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | Specifies the Windows operating system image to install. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **ImageInstall**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set the `ImageInstall` setting to install both an operating system image and a data image.

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

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
