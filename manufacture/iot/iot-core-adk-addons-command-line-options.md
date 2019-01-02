---

Description: 'These tools are part of the Windows 10 IoT Core (IoT Core) ADK Add-Ons, in the \\Tools folder. To learn more about these tools, see What''s in the Windows ADK IoT Core Add-ons.'
ms.assetid: ae043bb0-656e-4439-bdbe-a8d370629ab7
MSHAttr: 'PreferredLib:/library'
title: 'IoT Core Add-ons command-line options'

ms.date: 10/15/2018
ms.topic: article


---

# IoT Core Add-ons Powershell Commands

> [!NOTE]
> IoT Core Add-ons command-line is deprecated. Refer to [IoT Core Add-ons command-line options](https://github.com/ms-iot/iot-adk-addonkit/tree/17134/Docs/iot-core-adk-addons-command-line-options.md) for the old list of commands.

The Powershell version of the [Windows 10 IoT Core (IoT Core) ADK Add-Ons](https://github.com/ms-iot/iot-adk-addonkit/tree/master) supports the following commands. These are part of the powershell module [IoTCoreImaging](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging). To learn more about these tools, see [What's in the Windows ADK IoT Core Add-ons](iot-core-adk-addons.md).

## Powershell Commands with Alias

### [Add-IoTAppxPackage (newappxpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTAppxPackage.md)

Creates Appx OEM package and adds featureID to OEMFM.xml

### [Add-IoTBSP (newbsp)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTBSP.md)

Adds new bsp based on a template

### [Add-IoTBitLocker](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTBitLocker.md)

Adds bitlocker package for the product

### [Add-IoTCommonPackage (newcommonpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTCommonPackage.md)

Creates common (file/reg) OEM package and adds featureID to OEMCOMMONFM.xml

### [Add-IoTDeviceGuard](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTDeviceGuard.md)

Adds device guard package

### [Add-IoTDriverPackage (newdrvpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTDriverPackage.md)

Creates Driver OEM package and adds featureID to OEMFM.xml

### [Add-IoTFilePackage](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTFilePackage.md)

Adds a file package and adds the featureID to OEMCOMMONFM.xml

### [Add-IoTProductFeature (addfid)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTProductFeature.md)

Adds feature id to the product's oeminput xml file

### [Add-IoTProduct (newproduct)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTProduct.md)

Adds new product based on the OEMInputSamples from BSP

### [Add-IoTProvisioningPackage (newprovpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTProvisioningPackage.md)

Adds provisioning oem package and adds the featureID to OEMCOMMONFM.xml

### [Add-IoTRegistryPackage](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTRegistryPackage.md)

Adds a registry package and adds the featureID to OEMCOMMONFM.xml

### [Add-IoTSecureBoot](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTSecureBoot.md)

Adds secureboot package for the product

### [Add-IoTSecurityPackages](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTSecurityPackages.md)

Adds security packages for the product

### [Add-IoTSignature (signbinaries)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Add-IoTSignature.md)

Signs files with the cert set via Set-IoTSignature

### [Convert-IoTPkg2Wm (convertpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Convert-IoTPkg2Wm.md)

Converts pkg.xml files to wm.xml files

### [Copy-IoTBSP (copybsp)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Copy-IoTBSP.md)

Copies BSP between workspaces

### [Copy-IoTOEMPackage (copypkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Copy-IoTOEMPackage.md)

Copies OEM package between workspaces

### [Copy-IoTProduct (copyproduct)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Copy-IoTProduct.md)

Copies product between workspaces

### [Dismount-IoTFFUImage (ffud)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Dismount-IoTFFUImage.md)

Dismounts the FFU image

### [Export-IoTDUCCab (exportpkgs)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Export-IoTDUCCab.md)

Exports the update cab for DUC upload

### [Export-IoTDeviceModel (exportidm)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Export-IoTDeviceModel.md)

Exports the IoT Device Model for DUC registration

### [Export-IoTFFUAsWims (ffue)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Export-IoTFFUAsWims.md)

Exports the EFIESP/MainOS/Data partitions as Wims

### [Get-IoTFFUDrives (ffugd)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Get-IoTFFUDrives.md)

Returns a hashtable of the drive letters for the mounted partitions

### [Get-IoTProductFeatureIDs (gpfids)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Get-IoTProductFeatureIDs.md)

Gets features IDs supported in the IoTCore OS

### [Get-IoTProductPackagesForFeature (gpfidpkgs)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Get-IoTProductPackagesForFeature.md)

Gets OS packages corresponding to features ID

### [Get-IoTWorkspaceBSPs (gwsbsps)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Get-IoTWorkspaceBSPs.md)

Gets the list of BSP names in the workspace

### [Get-IoTWorkspaceProducts (gwsproducts)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Get-IoTWorkspaceProducts.md)

Gets the list of product names in the workspace

### [Import-IoTBSP (importbsp)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Import-IoTBSP.md)

Imports BSP from the given folder / zip file or sample workspace

### [Import-IoTCertificate](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Import-IoTCertificate.md)

Imports the certificate for security functions

### [Import-IoTDUCConfig (importcfg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Import-IoTDUCConfig.md)

Imports the CUSConfig.zip into the product directory

### [Import-IoTOEMPackage (importpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Import-IoTOEMPackage.md)

Imports OEM package from Sample workspace

### [Import-IoTProduct (importproduct)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Import-IoTProduct.md)

Imports Product from Sample workspace

### [Install-IoTOEMCerts](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Install-IoTOEMCerts.md)

Installs oem pfx files in the certs\private folder

### [Mount-IoTFFUImage (ffum)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Mount-IoTFFUImage.md)

Mounts the FFU image

### [New-IoTCabPackage (buildpkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTCabPackage.md)

Creates `.cab` files

### [New-IoTFFUCIPolicy (ffus)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTFFUCIPolicy.md)

Scans the MainOS partition and generates CI policy (`initialpolicy.xml`)

### [New-IoTFFUImage (buildimage)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTFFUImage.md)

Creates regular FFU

### [New-IoTFIPPackage (buildfm)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTFIPPackage.md)

Creates FIP packages and merged FM files

### [New-IoTInf2Cab (inf2cab)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTInf2Cab.md)

Creates cab file for the given inf file

### [New-IoTOEMCerts](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTOEMCerts.md)

Creates new OEM specific certificates

### [New-IoTProvisioningPackage (buildppkg)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTProvisioningPackage.md)

Creates `.ppkg` files

### [New-IoTRecoveryImage (buildrecovery)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTRecoveryImage.md)

Creates recovery FFU

### [New-IoTWindowsImage (newwinpe)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTWindowsImage.md)

Creates custom winpe with bsp drivers / recovery scripts

### [New-IoTWorkspace (new-ws)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/New-IoTWorkspace.md)

Creates new workspace

### [Open-IoTWorkspace (open-ws)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Open-IoTWorkspace.md)

Opens existing workspace

### [Redo-IoTCabSignature (re-signcabs)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Redo-IoTCabSignature.md)

Resigns cab and its contents using Add-IoTSignature

### [Redo-IoTWorkspace (migrate)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Redo-IoTWorkspace.md)

Converts legacy iot-adk-addonkit directory into a workspace

### [Remove-IoTProductFeature (removefid)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Remove-IoTProductFeature.md)

Removes feature id from the product's oeminput xml file

### [Set-IoTCabVersion (setversion)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Set-IoTCabVersion.md)

Stores the version in the IoTWorkspace.xml

### [Set-IoTEnvironment (setenv)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Set-IoTEnvironment.md)

Sets environment settings based on the config values in IoTWorkspace.xml

### [Set-IoTRetailSign (retailsign)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Set-IoTRetailSign.md)

Sets/resets use of the retail code signing certificate

### [Set-IoTSignature (setsignature)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Set-IoTSignature.md)

Sets the Certificate info used for signing

### [Test-IoTCabSignature](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Test-IoTCabSignature.md)

Tests if the Cab package and its contents are signed for the given config

### [Test-IoTFeatures](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Test-IoTFeatures.md)

Tests if all feature ids are defined, for the given product / config

### [Test-IoTPackages](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Test-IoTPackages.md)

Tests all packages and its contents are signed, for the given product / config

### [Test-IoTRecoveryImage (verifyrecovery)](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Test-IoTRecoveryImage.md)

Verifies if the wim files in the recovery ffu are proper

### [Test-IoTSignature](https://github.com/ms-iot/iot-adk-addonkit/tree/master/Tools/IoTCoreImaging/Docs/Test-IoTSignature.md)

Tests if the file is signed for the given config

## Related topics

[IoT Core Add-ons](iot-core-adk-addons.md)

[IoT Core Image Wizard](iot-core-image-wizard.md)

[IoT Core manufacturing guide](iot-core-manufacturing-guide.md)
