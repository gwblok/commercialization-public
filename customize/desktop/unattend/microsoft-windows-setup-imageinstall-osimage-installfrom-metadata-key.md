---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f22ee96d-c441-4f9d-960f-d22a27f33cf7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` is used with the setting: [Value](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-value.md) to choose which Windows image to install from a Windows image file (.wim). Windows image files may contain multiple Windows images. A Windows image may be selected by its index number, its name, or its description.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Values for <code>Key</code></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/IMAGE/INDEX</p></td>
<td><p>Uses the index number to select the image to install.</p></td>
</tr>
<tr class="even">
<td><p>/IMAGE/NAME</p></td>
<td><p>Uses the index name to select the image to install.</p></td>
</tr>
<tr class="odd">
<td><p>/IMAGE/DESCRIPTION</p></td>
<td><p>Uses the index description to select the image to install.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-osimage-installfrom.md) | [MetaData](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata.md) | **Key**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Examples


The following XML output shows how to configure the `MetaData` setting to install a specific Windows image using the image index value.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>2</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific Windows image using the image name.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/NAME</Key>
                <Value>Model FNB1</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific Windows image from a custom .wim file using the image description.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/DESCRIPTION</Key>
                <Value>Model FNB1</Value>
            </MetaData>
```

## Related topics


[MetaData](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata.md)

[Value](microsoft-windows-setup-imageinstall-osimage-installfrom-metadata-value.md)

 

 







