---
title: What's new in Windows 10, version 1809
description: New features for Windows 10, version 1809
ms.assetid: 1E8F0E54-1E5B-495B-848D-260620C7DF4F
ms.date: 11/29/2018
ms.topic: article


---
# What's new in Windows 10, version 1809

Welcome to Windows 10, version 1809! Here are some resources to get you acquainted with the new features and changes introduced for Windows device and driver creators in this version of Windows 10.

## New in design

| Topic         | Description                                                                            |
|:-----------------------|:----------------------------------------------------------------------|
| [Compatibility specifications](https://docs.microsoft.com/windows-hardware/design/compatibility/whcp-specifications-policies)           | The Windows Hardware Compatibility Program is designed to help your company deliver systems, software, and hardware products that are compatible with Windows and run reliably on Windows 10 and Windows Server. Windows 10 and Windows Server have updated specifications and policies available for download.     |

## New in driver development

| Topic                                      | Description                                                                                             |
|:-------------------------------------------|:--------------------------------------------------------------------------------------------------------|
|[Windows Hardware Dev Center dashboard](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#windows-hardware-dev-center-dashboard)    |We added new and improved functionality in the way of Hardware APIs for developers, IHVs, and OEMs to track and submit driver packages to the Windows hardware dashboard.     |
|[Open publishing](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#open-publishing)  | On many pages of the Windows driver documentation, you can suggest changes directly. Look for the Contribute button in the upper right corner of a page.   |
|[Debugging tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#debugging-tools-for-windows)|New Debugger Data Model API and support for IPV6.|
|[Device and driver installation](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#device-and-driver-installation)|Driver verifier includes new driver validation rules.|
|[Windows Driver Frameworks (WDF)](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#windows-driver-frameworks-wdf)|The Windows Driver Framework (WDF) includes Kernel-Mode Driver Framework (KMDF) version 1.27 and User-Mode Driver Framework version 2.27|
|[WPP Software Tracing](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development#wpp-software-tracing)|Introducing new feature: *Inflight Trace Recorder*. If the driver enables WPP tracing and WPP Recorder, trace logging is turned on automatically and you can easily view messages without starting or stopping trace sessions.|


> [!Tip]
> See [What's new in Driver development](https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development) for an in-depth look.


## New in manufacturing

| Topic | Description |
| --- | --- |
| [Deploy Push-button reset using Auto-apply folders](https://docs.microsoft.com/windows-hardware/manufacture/desktop/deploy-pbr-features-using-auto-apply) |  Auto-apply folders make configuring Push-button reset easier. |
| [Windows PE (WinPE)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/winpe-intro) | WinPE is no longer part of the ADK installer, and is now available as an add-on to the ADK | 
| [Add languages to Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/add-language-packs-to-windows) | Language interface pack (LIP) languages are now distributed as .appx files. Note, the [DISM /set-uilang and /set-allintl](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-languages-and-international-servicing-command-line-options) options are no longer supported for LIP languages. |
| [Available features on demand](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-non-language-fod) |  Several new Features on Demand are available |
| [Windows 10 IoT Core manufacturing](https://docs.microsoft.com/windows-hardware/manufacture/iot/iot-core-manufacturing-guide) | You can now create Windows IoT Core images using PowerShell. |
| [Recovery](https://docs.microsoft.com/windows-hardware/manufacture/desktop/prepare-recovery-tools) | WinPE is no longer part of the ADK installer, and is now available as an add-on to the ADK 
| [UEFI/GPT-based](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/configure-uefigpt-based-hard-drive-partitions)/[BIOS/MBR-based](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/configure-biosmbr-based-hard-drive-partitions) hard drive partitions | For drives larger than 128GB, we recommend that the recovery tools partition is at least 990MB. |


## New customization options

| Topic                                      | Description                                                                                             |
|:-------------------------------------------|:--------------------------------------------------------------------------------------------------------|
|[Retail Demo Mode](https://docs.microsoft.com/windows-hardware/customize/desktop/retail-demo-experience)| RDX 3.0 will be available soon. Connected devices will receive the update automatically.   |
|[Unified Write Filter](https://docs.microsoft.com/windows-hardware/customize/enterprise/unified-write-filter)| On devices with a disk overlay, you can use freespace passthrough to access your drive's additional free space. You can use a persistent overlay to allow data saved in the virtual overlay to remain even after a reboot.|
|[Adaptive Brightness](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-mobilepc-sensors-api-adaptivebrightness) | New settings for adaptive brightness: ALRCurveVersion, DefaultSliderPosition, and IsAutobrightnessEnabledByDefault. Adaptive brightness changes the brightness of a monitor or display based on the ambient light. |


## Related topics

[What's new in Windows 10, version 1809 for IT Pros](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
