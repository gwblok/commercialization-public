---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59b2d974-083f-4e99-b0d6-a7ae2f8d838e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies whether the image index, name, or description is used to specify the metadata for an image in a Windows image (.wim) file. For information about using this setting, see [MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md).

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


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [DataImage](microsoft-windows-setup-imageinstall-dataimage.md) | [InstallFrom](microsoft-windows-setup-imageinstall-dataimage-installfrom.md) | [MetaData](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata.md) | **Key**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Examples


The following XML output shows how to configure the `MetaData` setting to install a specific data image by using the image index value.

```
            <MetaData wcm:action="add">
                <Key>/IMAGE/INDEX</Key>
                <Value>1</Value>
            </MetaData>
```

The following XML output shows how to configure the `MetaData` setting to install a specific data image using the image name.

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

[Value](microsoft-windows-setup-imageinstall-dataimage-installfrom-metadata-value.md)











