---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: aa598368-b826-483d-9833-5dbaa6afd3f9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 12/14/2017
ms.topic: article


---
# Path

`Path` specifies the path to the data image to install. This can be either a local or a network path. If the path is local, no credentials are required.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_data_image</em></p></td>
<td><p>Specifies the path and the name of the data image to install. <em>Path_to_data_image</em> is a string.</p>
<p>Both local paths and Universal Naming Convention (UNC) paths are supported.</p>
<p>Relative paths are supported, but the name of the file must be specified. The path is relative to the path from where Windows Setup is run.</p>
<p>If the file path cannot be accessed because of an incorrect path or invalid credentials, installation is terminated.</p></td>
</tr>
</tbody>
</table>

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-dataimage-installfrom.md) | **Path**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML examples

### Network paths

The following XML example shows how to set the `ImageInstall` setting to install both an operating system image and a data image that are stored on a network.

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

### Relative paths

In the following XML example, the installer has the Windows installation programs, the Unattend file, and the data image on a USB drive, which is currently assigned to the drive letter E. The technician changes the working directory to E: before running Windows Setup.

```PowerShell
X:\Windows\System32> E:
E:\> setup.exe /installfrom:".\wims\32bitimage.wim" /unattend:".\autounattend_files\32bit_autounattend.xml"
```

```XML
<ImageInstall>
    <DataImage>
        <InstallFrom>
            <Path>.\wims\dataimage.wim</Path>
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>1</Value>
            </MetaData>
        </InstallFrom>
        <InstallTo>
            <DiskID>0</DiskID>
            <PartitionID>3</PartitionID>
        </InstallTo>
    </DataImage>
</ImageInstall>
```

### Absolute paths

You can reference an absolute path to your data image as follows:

`<Path>E:\dataimage.wim</Path>`

If the drive letter where Windows Setup resides is unknown, you can indicate this with the `%configsetroot%` variable. The following XML example shows how to use `%configsetroot%` to reference a local path where the drive letter where Windows Setup resides is unknown.

```XML
<DataImage wcm:action="add">
    <InstallTo>
        <DiskID>0</DiskID>
        <PartitionID>4</PartitionID>
    </InstallTo>
    <InstallFrom>
        <Path>%configsetroot%\dataimage.wim</Path>
        <MetaData wcm:action="add">
            <Key>/IMAGE/INDEX</Key>
            <Value>1</Value>
        </MetaData>
    </InstallFrom>
    <Order>1</Order>
</DataImage>
```

> [!Important]
> If using `%configsetroot%`, you must also set the value of the Unattend setting [Microsoft-Windows-Setup-UseConfigurationSet](microsoft-windows-setup-useconfigurationset.md) to `true`.

## Related topics

[InstallFrom](microsoft-windows-setup-imageinstall-dataimage-installfrom.md)

[Create a Data Image using DISM](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/create-a-data-image-using-dism)
