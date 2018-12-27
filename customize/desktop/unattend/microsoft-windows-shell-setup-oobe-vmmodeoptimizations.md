---
title: VMModeOptimizations
description: VMModeOptimizations
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 90E1B5C4-9234-4FB7-A7FD-0BB9AE3783C4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# VMModeOptimizations

`VMModeOptimizations` specifies settings you can use to customize the user experience when in VM mode.

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [SkipAdministratorProfileRemoval](microsoft-windows-shell-setup-oobe-vmmodeoptimizations-skipadministratorprofileremoval.md) | Use <code>SkipAdministratorProfileRemoval</code> to skip removal of the administrator profile when in VM mode. |
| [SkipNotifyUILanguageChange](microsoft-windows-shell-setup-oobe-vmmodeoptimizations-skipnotifyuilanguagechange.md) | Use <code>SkipNotifyUILanguageChange</code> in VM mode if the language will not change during setup. |
| [SkipWinREInitialization](microsoft-windows-shell-setup-oobe-vmmodeoptimizations-skipwinreinitialization.md) | Use <code>SkipWinREInitialization</code> in VM mode, particularly in a container scenario where recovery is not important, to skip initialization of the Windows Recovery Environment (Windows RE) image. |

## Valid configuration passes

oobeSystem

## Parent hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **VMModeOptimizations**

## Applies to

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML example

The following example shows how to set the VM mode optimization settings in the OOBE node of your Unattend.xml file.

```XML
            <OOBE>
                <VMModeOptimizations>
                    <SkipAdministratorProfileRemoval>true</SkipAdministratorProfileRemoval>
                    <SkipNotifyUILanguageChange>true</SkipNotifyUILanguageChange>
                    <SkipWinREInitialization>true</SkipWinREInitialization>
                </VMModeOptimizations>
            </OOBE>
```

> [!Note]
> You must specify `/mode:vm` during sysprep to fully enable this setting.
