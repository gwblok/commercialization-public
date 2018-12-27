---

Description: 'Features on Demand v2 (Capabilities), introduced in Windows 10, are Windows feature packages that can be added at any time. Common features include language resources like handwriting recognition or the .NET Framework (.NetFx3).'
ms.assetid: 6390f427-a201-487e-928f-964e7b84327c
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Features On Demand'

ms.date: 06/27/2018
ms.topic: article
ms.custom: RS5
---

# Features On Demand

## Overview

Features on Demand (FODs) are Windows feature packages that can be added at any time. Common features include [language resources](features-on-demand-language-fod.md) like handwriting recognition or [other features](features-on-demand-non-language-fod.md) like the .NET Framework (.NetFx3). When a Windows 10 PC needs a new feature, it can request the feature package from Windows Update. 

You can also preinstall FODs so they're ready if a user needs them. FODs are distributed as .cab files on the Feature on Demand ISO and you can use DISM to add a FOD to a Windows image. If you're using the FOD ISO to preinstall FODs, make sure you're using the FOD ISO that matches your Windows image version.

> [!Note]
> Add language packs, FODs, and apps, in that order, prior to installing an update. If you add an update prior to adding language packs, FODs, and apps you'll have to reinstall the update. 

## Types of Features on Demand

Starting with Windows 10, version 1809, Windows has two different types of Features on Demand:

| FOD type | Description | DISM Command |
| ---- | ---- | ---- |
| FODs without satellite packages | FODs with all language resources packaged into the same package. These FODs are distributed as a single .cab file. | `/add-package` or `/add-capability` |
| FODs with satellite packages | Language-neutral FODs that have language and/or architecture resources in separate packages (satellites). When you install this type of FOD, only the packages that apply to the Windows image are installed, which reduces disk footprint. These FODs are distributed as a set of several .cab files, but are installed by specifying a single `/capabilityname` These are new starting in Windows 10, version 1809. | `/add-capability`  |

- To install a Feature on Demand that has satellite packages, you have to add the feature on demand with `DISM /add-capability`, specifying the capability name. Unlike FODs without satellites, these new FODs can't be added as packages (`DISM /add-package`). 

- When adding a FOD with `/add-capability` to an offline image, you also have to specify a source with the `/source` option. You can use a mounted FOD ISO as the source, or you can create a FOD repository on local or network storage.


See [Available Features on demand](features-on-demand-non-language-fod.md) for more information about which FODs have satellites. Language FODs don't have satellites.

> [!Tip]
> While you can add non-satellite FODs using `/add-package`, we recommend adding all FODs with `/add-capability` because you can use it to add both satellite and non-satellite FODs.

## <span id="Adding_or_removing_features_capabilities"></span><span id="adding_or_removing_features_capabilities"></span><span id="ADDING_OR_REMOVING_FEATURES_CAPABILITIES"></span>Adding or removing Features on Demand

### Using DISM /add-package to add or remove FODs

You can add non-satellite Features on demand to a Windows image with `DISM /add-package`. The FODs that you can add with `/add-package` include the language FODs, the FODs that come preinstalled with Windows, and the FODs that we recommend for preinstallation. 

OEMs can generally add FODs to their Windows images using `DISM /add-package`, unless they need to preinstall a FOD that has satellites.

| Command | Description | Example |
| --- | --- | --- |
| /add-package | Adds a package, including a FOD .cab to an image. `add-package` can only be used to add FODs that don't have satellite packages. | `DISM.exe /image:C:\mount\Windows /add-package /packagepath:E:\Microsoft-Windows-Holographic-Desktop-FOD-Package~31bf3856ad364e35~amd64~~.cab` |
| /Get-Packages | Get a list of all packages in an image. | `DISM /image:C:\Mount\Windows /get-packages` |
| /Get-Packageinfo | Get information of a package in an image. | `DISM /image:C:\mount\Windows /get-packageInfo /packagename:Microsoft-Windows-Xps-Xps-Viewer-Opt-Package~31bf3856ad364e35~amd64~~10.0.17134.1000` |
| /Remove-Package | <p>Removes a package from an image.</p>**Note**: Don't remove a package that other packages depend on. For example, if you have the French handwriting and basic packages installed, don't remove the basic package.</p> | `DISM.exe /image:C:\mount\Windows /remove-capability /CapabilityName:Microsoft-Windows-Xps-Xps-Viewer-Opt-Package~31bf3856ad364e35~amd64~~10.0.17134.1000` |



### Using DISM /add-capability to add or remove FODs

You can also install FODs with `DISM /add-Capability`. You have to use `/add-capability` to preinstall satellite FODs. If you're preinstalling a FOD onto an offline image, use the `/source` option to tell Windows where to find the FOD installation files. The `/source` could be a FOD repository or a mounted FOD ISO. You can use multiple `/source` arguments in a command.

If you're adding a FOD to an online image, `/add-capability` downloads features from Windows Update and adds them to the image. If you don't want to install from Windows Update, you can use `/LimitAccess`, which tells DISM to not check Windows Update or Windows Server Update Services for the capability source files.

See [DISM Capabilities Package Servicing Command-Line Options](dism-capabilities-package-servicing-command-line-options.md) for more information.

-   Use the `/online` option to add the capability to your PC.
-   Use `/Image:\<mount path>` with the `/source` option to add the capability to a mounted Windows image.

 
| Command | Description | Example |
| --- | --- | --- |
| /add-capability | <p>Adds a capability to an image.</p><p>For packages with dependencies this also pulls dependent packages. For example, if you add the Speech package, you'll also get the Text-to-speech and Basic packages in addition to Speech.</p>DISM looks for source files in the following locations:<ol><li>If **/Source** is specified, DISM looks in the specified locations first.</li><li>If **/Source** is not specified, or if the source files are not found in the specified locations, DISM checks the locations specified by group policy.</li><li>If the files still aren't found, and if DISM is running against an online image, and if **/LimitAccess** is not specified, it looks for the files on Windows Update.</li></ol> | `DISM.exe /image:C:\mount\Windows /add-capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0 /Source:E:` <p>`DISM.exe /Online /add-capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0` |
| /Get-Capabilities | Get capabilities in the image. | `DISM /image:C:\Mount\Windows /Get-Capabilities` |
| /Get-CapabilityInfo | Get information of a capability in the image. | `DISM /image:C:\mount\Windows /Get-CapabilityInfo /CapabilityName:Language.Basic~~~en-US~0.0.1.0` |
| /Remove-Capability | <p>Removes a capability from an image.</p>**Note**: You cannot remove a capability that other packages depend on. For example, if you have the French handwriting and basic capabilities installed, you can't remove the basic capability.</p> | `DISM.exe /image:C:\mount\Windows /Remove-Capability  /CapabilityName:Language.Basic~~~en-US~0.0.1.0` |

To see all available DISM commands for capabilities, see [DISM Capabilities Package Servicing Command-Line Options](dism-capabilities-package-servicing-command-line-options.md).


## <span id="related_topics"></span>Related topics

* [Available Features on Demand](features-on-demand-non-language-fod.md)
* [Language and region Features on Demand](features-on-demand-language-fod.md)
* [Add Language Packs to Windows](add-language-packs-to-windows.md)
* [DISM Capabilities Package Servicing Command-Line Options](dism-capabilities-package-servicing-command-line-options.md)
