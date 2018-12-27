---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 14569bdd-ebe0-496c-9b44-3092e0f3e90f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` is used with the setting: [Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md) to choose which Windows image to install from a Windows image file (.wim). Windows image files may contain multiple Windows images. The `Value` may identify a Windows image by its index number, its name, or its description.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>Specifies a value for the setting: <a href="microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md" data-raw-source="[Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md)">Key</a>.</p>
<p><em>Value</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-osimage-installfrom.md) | [MetaData](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata.md) | **Value**

## Applies To


For the list of Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Examples


The following XML output shows how to configure the `MetaData` setting to install a specific Windows image from a Windows image (.wim) file using the image index value.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>2</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific Windows image from a custom Windows image (.wim) file using the image name.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/NAME</Key>
                <Value>Model FNB1</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific Windows image from a custom Windows image (.wim) file using the image description.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/DESCRIPTION</Key>
                <Value>Model FNB1</Value>
            </MetaData>
```

## Related topics


[MetaData](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata.md)

[Key](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-key.md)

 

 







