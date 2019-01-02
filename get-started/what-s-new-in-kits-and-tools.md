---
title: What's new in the Windows ADK and ADK tools
description: What's new in Windows ADK and ADK tools
Search.SourceType: Video
ms.assetid: EE27ABF7-C197-4E8E-AC1B-77266E2B9FD9
ms.date: 04/30/2018
ms.topic: article


---
# What's new in ADK kits and tools

## What's new in the Windows ADK for Windows 10, version 1809

### Windows PE

Starting with Windows 10, version 1809, Windows Preinstallation Environment (PE) is released separately from the Assessment and Deployment Kit (ADK). To add Windows PE to your ADK installation, download the Windows PE Addon and run the included installer after installing the ADK. This change enables post-RTM updates to tools in the ADK. After running the installer for the WinPE add-on, the WinPE files will be in the same location as they were in previous installs of the ADK.

See [Download and install the Windows ADK and ADK tools](adk-install.md) to get the ADK and WinPE add-on.

### WPT

With the latest version of Windows Performance Recorder (WPR), WPR Profiles (WPRP) with Custom Events in TraceMergeProperties now work as intended.  Due to this change, if a custom WPRP contains an TraceMergeProperties XML element with an empty set of Custom Events, this will no longer include the default set of Custom Events (ImageIDs, WinSat, etc).
To keep the same behavior with previous versions, make sure to include the following attribute as part of the TraceMergeProperties element:
Base=”TraceMerge_Default” 

With the latest version of Windows Performance Analyzer (WPA), .NET 4.5.2 framework is required for certain components when running on Windows 8 installations.  To ensure proper use of WPA, [download the latest version of .NET](https://www.microsoft.com/en-us/download/details.aspx?id=48130).

## Retail Demo Experience (RDX)

[RDX 3.0 is available in Windows 10, version 1809](https://docs.microsoft.com/windows-hardware/customize/desktop/retail-demo-experience), and will be automatically updated on Windows 10, version 1803 for connected devices. Updates include a new webpage-style layout, a new API to allow you to manage your own assets, and a digital fact tag that can be updated locally from the sales floor.

### Answer file setting changes

For an overview of Unattend settings that are new, deprecated, and removed, see [Changed answer file settings for Windows 10, version 1809 for desktop editions](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/changed-answer-file-settings-for-windows-10-build-1809).

To learn more, see [Unattended Windows Setup Reference](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/).

## What's new in the Windows ADK for Windows 10, version 1803

### PowerView

PowerView is a new tool used to visualize data from Energy Estimation Engine logs produced by [powercfg /srumutil](https://docs.microsoft.com/windows-hardware/design/device-experiences/powercfg-command-line-options#option_srumutil), and Windows Assessment Toolkit battery life tests.

### New in Windows Assessment Toolkit

* Standby (S3) and Hibernate (S4) battery life workloads
* Productivity Workload (prerequisite: install Microsoft Office 2016 before executing the test)
* Modern Standby Performance

See [Windows Assessment Toolkit](https://docs.microsoft.com/en-us/windows-hardware/test/assessments/) for guidance.

### Answer file setting changes

For an overview of Unattend settings that are new, deprecated, and removed, see [Changed answer file settings for Windows 10, version 1803 for desktop editions](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/changed-answer-file-settings-for-windows-10-build-1803).

To learn more, see [Unattended Windows Setup Reference](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/).

### MDM: Enhanced device and PC management

Check out the [new CSPs settings](https://docs.microsoft.com/windows/client-management/mdm/new-in-windows-mdm-enrollment-management#whatsnew1803).

See [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/) for more information.

### More changes

See [What's new in Windows 10](what-s-new-in-windows.md) for the latest features and changes in design, customization, manufacturing, and drivers.

## What’s new in the Windows ADK for Windows 10, version 1709

### Support for ARM64 platforms

### Answer file setting changes

For an overview of Unattend settings that are new, deprecated, and removed, see [Changed answer file settings for Windows 10 version 1709 for desktop editions](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/desktop/unattend/changed-answer-file-settings-for-windows-10-build-1709).

To learn more about Unattend settings, see the [Unattended Windows Setup Reference](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/unattend/).

### MDM: Enhanced device and PC management

Check out the [new CSPs settings](https://docs.microsoft.com/en-us/windows/client-management/mdm/new-in-windows-mdm-enrollment-management#whatsnew1709).

See [Mobile Device Management](https://docs.microsoft.com/en-us/windows/client-management/mdm/) for more information.

### More changes

See [What's new in Windows 10](what-s-new-in-windows.md) for the latest features and changes in design, customization, manufacturing, and drivers.

> [!TIP]
> Watch our video on [ADK, HLK, HDK and EWDK updates for the Windows 10 Fall Creators Update](https://channel9.msdn.com/Events/WinHEC/WinHEC-Online/ADK-HLK-HDK-and-EWDK-updates-for-the-Windows-10-Fall-Creators-Update) to learn more.

## Learn about the ADK tools

The topics below provide instructions on using the tools included in the Windows 10 ADK:

* [Windows Configuration Designer](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-packages)
* [Windows Preinstallation Environment (WinPE)](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-intro)
* [Deployment Image Servicing and Management (DISM)](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
* [Windows System Image Manager (WSIM)](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/windows-system-image-manager-technical-reference)
* [Windows Assessment Toolkit](https://docs.microsoft.com/en-us/windows-hardware/test/assessments/)
* [Windows Performance Toolkit](https://docs.microsoft.com/en-us/windows-hardware/test/wpt/)
* [User State Migration Toolkit (USMT)](https://docs.microsoft.com/en-us/windows/deployment/usmt/usmt-reference)
* [Volume Activation Management Tool (VAMT)](https://docs.microsoft.com/en-us/windows/deployment/volume-activation/volume-activation-management-tool)
* [User Experience Virtualization (UE-V)](https://docs.microsoft.com/en-us/windows/configuration/ue-v/uev-for-windows)
* [Application Virtualization (App-V)](https://docs.microsoft.com/en-us/windows/application-management/app-v/appv-for-windows)

> [!Tip]
> You can find ADK tools located in the following directory:
> `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit`

## What’s new in the Windows ADK for Windows 10, version 1703

### Windows Configuration Designer

Previously known as Windows Imaging and Configuration Designer (ICD), the tool for creating provisioning packages is renamed Windows Configuration Designer. Windows Configuration Designer in Windows 10, version 1703, includes several new wizards to make it easier to create provisioning packages.

### New answer file settings added

To see the newest unattend settings, go to [Changed answer file settings for Windows 10 version 1703 for desktop editions.](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/desktop/unattend/changed-answer-file-settings-for-windows-10-build-1703)

### MDM: Enhanced device and PC management

Check out the [new CSPs settings](https://docs.microsoft.com/en-us/windows/client-management/mdm/new-in-windows-mdm-enrollment-management#a-href-idwhatsnew10awhats-new-in-windows-10-version-1703).

## What’s new in the Windows ADK for Windows 10, version 1607

### Pick and choose desktop applications

With [siloed provisioning packages](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/siloed-provisioning-packages), you can now pick and choose which desktop applications to add to your images during deployment. You no longer need to recapture the entire set of applications into your recovery image, they’re added in automatically. These packages support space-saving features like Compact OS and single-instancing. 

### Build IoT Core images for large-scale deployment

Capture your apps, drivers, and settings, and deploy them securely to new devices. Learn how with the [IoT Core manufacturing guides](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/iot/iot-core-manufacturing-guide).

### The Chinese (Hong Kong SAR) language pack (zh-HK) is no longer used.

The Chinese (Taiwan) language pack (zh-TW) supports both Taiwan and Hong Kong locales. For more information, see Available Language Packs for Windows.

### You can limit access to a single Windows app (assigned access)

* [Configure Assigned Access](https://msdn.microsoft.com/library/windows/hardware/mt620043)

### New answer file settings added

* Add more tiles to the Start Menu: [SquareOrDesktopTile7](https://msdn.microsoft.com/library/windows/hardware/dn915881) through [SquareOrDesktopTile12](https://msdn.microsoft.com/library/windows/hardware/dn915868)
* Add an [advanced pen settings app](https://msdn.microsoft.com/library/windows/hardware/mt757353)
* Allow a [chat window in a remote access session](https://msdn.microsoft.com/library/windows/hardware/mt752384)
* Set [auto-brightness controls](https://msdn.microsoft.com/library/windows/hardware/dn757391)
* See more [new answer file settings](https://msdn.microsoft.com/library/windows/hardware/mt750416.aspx)

### MDM: Enhanced device and PC management

Check out the [new CSPs settings](https://msdn.microsoft.com/en-us/library/windows/hardware/mt299056.aspx#whatsnew_1607).

## What’s new in the Windows ADK for Windows 10, version 1511

The Windows ADK now includes [Windows Imaging and Configuration Designer](https://msdn.microsoft.com/library/windows/hardware/dn916113.aspx), the [Windows Assessment Toolkit](https://msdn.microsoft.com/windows/hardware/commercialize/test/assessments/index), the [Windows Performance Toolkit](https://msdn.microsoft.com/windows/hardware/commercialize/test/wpt/index), and several new and improved deployment tools that can help you automate a large-scale deployment of Windows 10.

### Windows Imaging and Configuration Designer (ICD)

* Quickly create a provisioning package that you can use to customize devices without re-imaging.
* Build a customized Windows 10 image for specific market segments and regions.

See [Getting started with Windows ICD](https://msdn.microsoft.com/library/windows/hardware/dn916112.aspx) for more information.

### Push-button reset incorporates system updates by default

Users can now refresh or restore their PCs to the updated version of the system files, instead of having to reinstall each update individually.

### Partial language packs now available

Want to add more languages for users when they turn on their device? Instead of adding full language packs, save space by adding just the base user interface files for a language. Later, if your user needs handwriting or voice recognition capabilities, Windows can download them as needed.

For more information, see [Language Packs (lp.cab)](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/language-packs-and-windows-deployment).

### New package type: Capabilities

This new Windows package type lets you request services like Microsoft .NET or languages without specifying the version. Use the DISM tool to search multiple sources like Windows Update or your corporate servers to find and install the latest version.

### Save space by running Windows from compressed OS files

You can now run Windows directly from compressed files. This is similar to WIMBoot, introduced in Windows 8.1 Update 1. This new process uses individual files instead of a static WIM file. When updating system files, Windows now replaces the old files instead of keeping both copies.

## Related topics

* [Kits and tools overview](kits-and-tools-overview.md)
* [What's new in driver development](https://msdn.microsoft.com/windows/hardware/drivers/what-s-new-in-driver-development)
* [What's new in the Windows Performance Toolkit](https://msdn.microsoft.com/en-us/library/windows/hardware/dn927303.aspx)
* [What's new in the Hardware Lab Kit](https://msdn.microsoft.com/library/windows/hardware/mt187880.aspx)
