---
title: DataImage
description: DataImage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 51447b7a-7d62-4a7f-9a62-a4cb9d21513e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DataImage

`DataImage` specifies a data image to install. You can add data on top of a Windows operating system image by using a data image. Data images can include applications, device drivers, and other configuration files. You can create a data image by using ImageX.

You should never use a data image to overwrite Windows system data. Use data images only to add files.

There can be more than one data image. The [OSImage](microsoft-windows-setup-imageinstall-osimage.md) is installed before any data images.

> [!Note]
> The [MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md) settings are required.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [InstallFrom](microsoft-windows-setup-imageinstall-dataimage-installfrom.md) | Required. Specifies the location from which to install the data image. |
| [InstallTo](microsoft-windows-setup-imageinstall-dataimage-installto.md) | Required. Specifies the location to which to install the data image. |
| [Order](microsoft-windows-setup-imageinstall-dataimage-order.md) | Required. Specifies the order in which to install the data image. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | **DataImage**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

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

[ImageInstall](microsoft-windows-setup-imageinstall.md)

[Create a Data Image using DISM](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/create-a-data-image-using-dism)
