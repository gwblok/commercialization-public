---
title: Microsoft-Windows-Setup
description: Microsoft-Windows-Setup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1a4a4656-9f87-478e-b905-dd91c40562b5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-Setup

The Microsoft-Windows-Setup component contains settings that enable you to select the Windows image that you install, configure the disk that you install Windows to, and configure the Windows PE operating system.

Some of the settings in this component apply only to Windows PE, and some settings are applied to the installed Windows image. Each setting describes which operating system the setting applies to.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[ComplianceCheck](microsoft-windows-setup-compliancecheck.md)|Checks that the requirements for installing Windows are fulfilled so that the operating system can be installed.|
|[Diagnostics](microsoft-windows-setup-diagnostics.md)|Specifies whether to send installation information to Microsoft.|
|[DiskConfiguration](microsoft-windows-setup-diskconfiguration.md)|Specifies the disk configurations to apply to a disk on the destination computer.|
|[Display](microsoft-windows-setup-display.md)|Specifies display settings to apply to Windows PE.|
|[DynamicUpdate](microsoft-windows-setup-dynamicupdate.md)|Specifies whether to enable dynamic updates.|
|[EnableFirewall](microsoft-windows-setup-enablefirewall.md)|Specifies whether to enable Windows Firewall for Windows PE.|
|[EnableNetwork](microsoft-windows-setup-enablenetwork.md)|Specifies whether a network connection is enabled.|
|[ImageInstall](microsoft-windows-setup-imageinstall.md)|Specifies the Windows image to install.|
|[LogPath](microsoft-windows-setup-logpath.md)|Specifies the path used for log files during Windows PE.|
|[PageFile](microsoft-windows-setup-pagefile.md)|Specifies the size and the location of the page file used during Windows PE.|
|[Restart](microsoft-windows-setup-restart.md)|Specifies whether to restart or shut down the computer after Windows PE completes.|
|[RunAsynchronous](microsoft-windows-setup-runasynchronous.md)|Specifies commands to run asynchronously after Windows PE starts.|
|[RunSynchronous](microsoft-windows-setup-runsynchronous.md)|Specifies commands to run synchronously after Windows PE starts.|
|[UpgradeData](microsoft-windows-setup-upgradedata.md)|Specifies whether the installation is an upgrade of an existing operating system.|
|[UseConfigurationSet](microsoft-windows-setup-useconfigurationset.md)|Specifies that a configuration set is used.|
|[UserData](microsoft-windows-setup-userdata.md)|Specifies user data, such as the user name and the product key to apply to the Windows installation.|
|[WindowsDeploymentServices](microsoft-windows-setup-windowsdeploymentservices.md)|Specifies settings for Windows Deployment Services, a management tool designed to facilitate deployment with a limited number of settings.|

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
