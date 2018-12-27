---
title: DisableEncryptedDiskProvisioning
description: DisableEncryptedDiskProvisioning
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 368c6dc6-6308-4354-9ca4-b9c2db89a74b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableEncryptedDiskProvisioning


`DisableEncryptedDiskProvisioning` specifies whether Windows activates encryption on blank drives that are capable of hardware-based encryption during installation.

By default, Windows activates drives that are capable of hardware-based encryption by using a fixed access control list (ACL) that is based on the Opal Security Subsystem Class (Opal SSC) specification.

**Note**  
Use the [TCGSecurityActivationDisabled](microsoft-windows-enhancedstorage-adm-tcgsecurityactivationdisabled.md) unattend setting to enable the Group Policy setting, **Do not automatically encrypt files moved to encrypted folders**, after Windows is installed and started up. The setting specifies, for unprovisioned eDrives, whether security should be activated on the eDrive during provisioning.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that Windows does not activate encryption on blank drives, even if those drives are capable of hardware-based encryption.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that Windows activates encryption on blank drives that are capable of hardware-based encryption. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DiskConfiguration](microsoft-windows-setup-diskconfiguration.md) | **DisableEncryptedDiskProvisioning**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output for the `DisableEncryptedDiskProvisioning` setting shows how to specify that Windows does not activate encryption on blank drives, even if those drives are capable of hardware-based encryption.

```
<DisableEncryptedDiskProvisioning>true</DisableEncryptedDiskProvisioning>
```

## Related topics


[DiskConfiguration](microsoft-windows-setup-diskconfiguration.md)

[TCGSecurityActivationDisabled](microsoft-windows-enhancedstorage-adm-tcgsecurityactivationdisabled.md)

 

 







