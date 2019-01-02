---
title: Compact
description: Compact
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: DF11A73C-3F8F-4C11-9623-59E74AB29488
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Compact


Specifies whether the Windows image should be applied with compression enabled during installation. If set to **true**, files written to the disk during installation are compressed individually, which allows Windows to take up less disk space.

**Note**  
If the **Compact** setting is set to true, you must start Windows Setup from Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), from a previous version of Windows with the Windows 10 Assessment and Deployment Kit (ADK) installed, or from the Windows 10 version of the Windows Preinstallation Environment (PE). If you are using a previous version of Windows PE, the Windows overlay filter driver (wofadk.sys) from the Windows 10 ADK must be included in the Windows PE image.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that Windows should be installed with compression enabled. This might cause the installation process to take longer.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that Windows should be installed with compression disabled.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ImageInstall](microsoft-windows-setup-imageinstall.md) | [OSImage](microsoft-windows-setup-imageinstall-osimage.md) | **Compact**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## Related topics


[OSImage](microsoft-windows-setup-imageinstall-osimage.md)

 

 







