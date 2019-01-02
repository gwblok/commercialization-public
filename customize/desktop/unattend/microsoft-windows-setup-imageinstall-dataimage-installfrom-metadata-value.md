---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 05f5d2c1-7927-4225-a8e4-2d99ebe31195
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the value for the [Key](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata-key.md) setting. For information about using this setting, see [MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Windows_image_description</em></p></td>
<td><p>Specifies the value of the <code>Key</code> setting. <em>Windows_image_description</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-dataimage-installfrom.md) | [MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md) | **Value**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Examples


The following XML output shows how to configure the `MetaData` setting to install a specific data image by using the image index value.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>2</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific data image by using the image name.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/NAME</Key>
                <Value>FNB2Drivers</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific data image by using the image description.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/DESCRIPTION</Key>
                <Value>FabriKam Model FNB3 Drivers</Value>
            </MetaData>
```

## Related topics


[MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md)

[Key](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata-key.md)

 

 







