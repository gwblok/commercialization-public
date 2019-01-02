---
title: Upgrade
description: Upgrade
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ff8f3677-a876-4510-9073-e51a45054241
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Upgrade


`Upgrade` specifies whether the present installation is an upgrade from a previous version of Windows.

Windows Setup does not support using any other unattended Setup settings during upgrades. When you upgrade from an earlier version of Windows, you must create an answer file that includes only the Windows-Setup\\`UpgradeData` settings. Then, you must use either the Windows product DVD or the System Preparation (Sysprep) tool to upgrade Windows.

For a sample answer file, see the [XML Example](#xmlexample) section.

**Caution**  
If you use an installation image that was originally installed by using an Unattend.xml file, and you execute the **Repair in-place upgrade (overwrite installation)** option, the upgrade installation may quit. You may not be able to restart the installation. For more information, see [Knowledge Base Article ID 2425962](http://go.microsoft.com/fwlink/?LinkId=209802).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the present installation is an upgrade.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the present installation is not an upgrade. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [UpgradeData](microsoft-windows-setup-upgradedata.md) | **Upgrade**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## <a href="" id="xmlexample"></a>XML Example


The following XML output shows how to set an upgrade installation to run in guaranteed quiet mode.

```
<UpgradeData>
   <Upgrade>true</Upgrade>
   <WillShowUI>Never</WillShowUI>
</UpgradeData>
```

## Related topics


[UpgradeData](microsoft-windows-setup-upgradedata.md)

 

 







