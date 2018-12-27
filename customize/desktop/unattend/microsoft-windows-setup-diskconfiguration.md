---
title: DiskConfiguration
description: DiskConfiguration
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 25509a92-38c8-45e7-9fed-19a5b0ec09cf
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DiskConfiguration

`DiskConfiguration` contains the settings that Windows uses to partition and to configure one or more physical hard disks.

Valid disk partition configurations vary depending on whether you are using a BIOS-based computer or a Unified Extensible Firmware Interface (UEFI)-based computer. For more information, see the [Manage Hard Disks and Partitions](http://go.microsoft.com/fwlink/?LinkId=206671) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

You can configure disk partitions manually in the disk configuration user interface (UI) in Windows Setup, or automatically by using settings in the [Disk](microsoft-windows-setup-diskconfiguration-disk.md) element. If you do not specify a `Disk` element and the [WillShowUI](microsoft-windows-setup-diskconfiguration-willshowui.md) setting is set to **Never**, Windows logs an error, and the installation terminates.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DisableEncryptedDiskProvisioning](microsoft-windows-setup-diskconfiguration-disableencrypteddiskprovisioning.md) | Specifies whether Windows activates encryption on blank drives that are capable of hardware-based encryption. |
| [Disk](microsoft-windows-setup-diskconfiguration-disk.md) | Specifies the disk configurations to apply to a disk on the destination computer. |
| [WillShowUI](microsoft-windows-setup-diskconfiguration-willshowui.md) | Specifies whether to show the disk configuration UI in Windows Setup. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **DiskConfiguration**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Examples

### Manual Configuration

The following XML output for the `DiskConfiguration` setting shows how to specify that you will configure disk partitions manually through the disk configuration UI in Windows Setup:

```XML
<DiskConfiguration>
   <WillShowUI>Always</WillShowUI>
</DiskConfiguration>
```

For full XML examples and recommended partition configurations, see [How to Configure UEFI/GPT-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214261) or [How to Configure BIOS/MBR-Based Hard Disk Partitions](http://go.microsoft.com/fwlink/?LinkId=214260).

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
