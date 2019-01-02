---
title: TCGSecurityActivationDisabled
description: TCGSecurityActivationDisabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f9ace2c5-cfc4-451b-b635-a8a9bc6594fb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# TCGSecurityActivationDisabled

`TCGSecurityActivationDisabled` specifies whether Windows automatically configures encrypted drives (eDrives), also known as encrypted hard disk drives (eHDDs).

`TCGSecurityActivationDisabled` sets the Group Policy administrative template setting: **Do not automatically encrypt files moved to encrypted folders**. This Group Policy setting is used after Windows is installed and started up. The setting specifies, for unprovisioned eDrives, whether security should be activated on the eDrive during provisioning. Use the [DisableEncryptedDiskProvisioning](microsoft-windows-setup-diskconfiguration-disableencrypteddiskprovisioning.md) unattend setting for configuring the operating system installation for the target HDD.

> [!Note]
> The eDrive must be configured in the unattend file by using the settings in microsoft-windows-setup-\\DiskConfiguration\\Disk. If the drives are configured manually, then the eDrive configuration policy may not be properly configured.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that Windows does not automatically encrypt eDrives.</p></td>
</tr>
<tr class="even">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that Windows automatically encrypts eDrives. This is the default value.</p></td>
</tr>
</tbody>
</table>

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-EnhancedStorage-Adm](microsoft-windows-enhancedstorage-adm.md) | **TCGSecurityActivationDisabled**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-EnhancedStorage-Adm](microsoft-windows-enhancedstorage-adm.md).

## XML Example

The following XML output shows how to configure Windows so that Windows does not automatically encrypt eDrives.

```XML
<TCGSecurityActivationDisabled>1</TCGSecurityActivationDisabled>
```

## Related topics

[Encrypted Drives (eDrive) Reference](http://go.microsoft.com/fwlink/?LinkId=217371)

[Microsoft-Windows-EnhancedStorage-Adm](microsoft-windows-enhancedstorage-adm.md)

[DisableEncryptedDiskProvisioning](microsoft-windows-setup-diskconfiguration-disableencrypteddiskprovisioning.md)

[DiskConfiguration](microsoft-windows-setup-diskconfiguration.md)
