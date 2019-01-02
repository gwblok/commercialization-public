---
title: ComplianceCheck
description: ComplianceCheck
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d37403a5-04d0-417c-8309-66d58397af12
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ComplianceCheck

`ComplianceCheck` checks that the following requirements are fulfilled so that Windows can be installed:

* Valid hardware configuration.
* Power management disabled.
* No cluster sizes of larger than 4 kilobytes (KB).
* In-box drivers available.
* Product key matches available hardware. Windows 7 Starter and Windows Vista Starter can be installed only on the following types of central processing unit (CPU):

  * Intel Celeron and Intel Pentium III processors, including mobile versions, except for Intel Pentium III Xeon processors.
  * AMD Duron, AMD Sempron, and AMD Geode processors, including mobile versions.
  * 64-bit processors work only if they belong to one of the processors listed above. However, such processors are limited to 32-bit mode.

* No SMART failures on installation disk.
* Sufficient disk space.
* Valid operating system or Windows Preinstallation Environment (Windows PE).
* All run-once items have finished.
* There is no pending reboot on the computer.

`ComplianceCheck` also checks that the existing operating system is one of the following:

* Windows 2000, Service Pack 4 or later.
* Windows XP, Service Pack 2 or later.
* Windows Server 2000, Service Pack 1 or later.
* Windows Server 2003.
* Windows Server 2008.
* Windows Server 2008 R2.
* Windows Vista.
* Windows 7.

> [!Important]
> `ComplianceCheck` does not validate application compatibility. See the software vendor for application compatibility requirements.

The user is also warned if any of the following conditions apply (provided [DisplayReport](microsoft-windows-setup-compliancecheck-displayreport.md) is set to **OnError**). Otherwise, the user must boot from installation media and perform a clean installation instead of an upgrade.

* There are SMART failures, and no alternate disk is available.
* There is insufficient space for temporary files for Windows Setup or for total installation.
* A newer version of the loader is already on the destination computer. This applies to dual-boot scenarios only.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DisplayReport](microsoft-windows-setup-compliancecheck-displayreport.md) | A string that specifies in what circumstances the user interface (UI) is displayed for this item. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **ComplianceCheck**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output changes the `ComplianceCheck` setting to run in guaranteed quiet mode.

```XML
<ComplianceCheck>
   <DisplayReport>Never</DisplayReport>
</ComplianceCheck>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
