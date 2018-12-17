---
author: kpacquer
Description: Prepare recovery tools for your Windows images
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Prepare recovery tools for your Windows images
ms.author: kenpacq
ms.date: 11/16/2018
ms.topic: article
ms.custom: RS5
---

# Prepare recovery tools for your Windows images

When you’re creating Windows 10 and Windows Server images, update the recovery tools.

## [Windows Recovery Environment (Windows RE)](windows-recovery-environment--windows-re--technical-reference.md)
Both Windows 10 and Windows Server include a recovery environment that can repair common causes of unbootable operating systems.

Some customizations that you add to Windows should also be added to Windows RE to help make sure the systems can be restored:

| Customization | What do I need to update? | 
|---------------|---------------------------|
| **Boot-critical drivers** or **languages** | If you add these to your Windows image, [add those same drivers and languages (when available) to Windows RE](customize-windows-re.md). |
| **Custom recovery tools** | [Add a custom tool to the Windows RE boot options menu](add-a-custom-tool-to-the-windows-re-boot-options-menu.md) | 
| **Dedicated hardware button** | [Add a dedicated hardware button to boot immediately to WinRE](add-a-hardware-recovery-button-to-start-windows-re.md) |

More options:

* [Deploy Windows RE](deploy-windows-re.md): If you're deploying Windows using a .wim file, use these instrutions to deploy the recovery partition and hide the recovery drive letters.



## [Push-button reset](push-button-reset-overview.md)
Windows 10 users can reset their device, either keeping data and apps intact or resetting it for a new user. 

With a separate bare metal reset USB key, users can reset their devices when replacing the hard drive.

Some OEM customizations require additional steps to make sure that they get restored during a reset operation:

| Customization | What do I need to update? |
|------------|---------------------------|
|**Universal Windows apps** | Automatically restored. |
| **Drivers** installed using an .inf file | Automatically restored. |
| **Windows desktop apps**, or **drivers** installed using an .exe file | [Capture into a provisioning package](deploy-push-button-reset-features.md). (Apps and drivers installed as [siloed provisioning packages (SPPs)](siloed-provisioning-packages.md) are automatically restored.)|
| **Out of Box Experience customizations**, the **Start Menu**, and **Unattend.xml settings** | In Windows 10, version 1809, save a copy in your [Auto-apply folders](recovery-strategy-for-common-customizations.md#auto-apply). In earlier versions or as an alternative, use [extensibility scripts](recovery-strategy-for-common-customizations.md#restoring_settings_using_unattend.xml_and_extensibility_scripts) instead. |
| **Drive partitions** | If your device uses a non-standard drive partition layout, [update bare-metal reset so users can create their own recovery media](bare-metal-resetrecovery-enable-your-users-to-create-media-and-to-recover-hard-drive-space.md). |
| Ship **USB recovery media** to customers | [Bare metal reset/recovery: create recovery media while deploying new devices](create-media-to-run-push-button-reset-features-s14.md). |

More options: 

* Use [Compact OS, single-sourcing, and image optimization](compact-os.md) to save space on the disk.

## Reference
* [How push-button reset features work](how-push-button-reset-features-work.md)
* [Push-button reset frequently-asked questions (FAQ)](pbr-faq.md)
* [REAgentC command-line options](reagentc-command-line-options.md)
* [ResetConfig XML reference](resetconfig-xml-reference-s14.md)
* [WinREConfig XML reference](winreconfig-xml-reference.md)
* [Windows RE troubleshooting features](windows-re-troubleshooting-features.md)
