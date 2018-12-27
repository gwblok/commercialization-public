---
title: Download and install the Windows ADK
Description: Instructions on how to download and install the Windows ADK
MSHAttr: 'PreferredLib:/library/windows/hardware'
ms.date: 09/10/2018
ms.topic: article
---
# Download and install the Windows ADK

The Windows Assessment and Deployment Kit (Windows ADK) has the tools you need to customize Windows images for large-scale deployment, and to test the quality and performance of your system, its added components, and the applications running on it. The Windows ADK includes:

* The Windows Assessment Toolkit and the Windows Performance Toolkit to assess the quality and performance of systems or components.
* Deployment tools such as WinPE, Sysprep, and other tools that you can use to customize and deploy Windows 10 images.
* Starting with Windows 10, version 1809, Windows Preinstallation Environment (PE) is released separately from the Assessment and Deployment Kit (ADK). To add Windows PE to your ADK installation, download the Windows PE Addon and run the included installer after installing the ADK. This change enables post-RTM updates to tools in the ADK. After you run the installer, the WinPE files will be in the same location as they were in previous ADK installs.

> [!div class="nextstepaction"]
> [Download the Windows ADK for Windows 10, version 1809](https://go.microsoft.com/fwlink/?linkid=2026036)

> [!div class="nextstepaction"]
> [Download the Windows PE add-on for the ADK](https://go.microsoft.com/fwlink/?linkid=2022233)

[What's new in ADK tools for Windows 10, version 1809](what-s-new-in-kits-and-tools.md).

For Windows 10 IoT Core, also [download the IoT Core Add-Ins](https://github.com/ms-iot/iot-adk-addonkit/).

## Other ADK downloads

| ADK version and download link                                                                              | Description                                                                                                                                                                                                                                                                                                     |
|:-----------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [ADK for Windows 10 Insider Preview](https://www.microsoft.com/software-download/windowsinsiderpreviewADK) | Windows Insiders can download preview versions of the ADK. [See what's new for Windows Insiders for Business](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/wip-4-biz-whats-new).                                                                                                                |
| [ADK for Windows 10, version 1803](https://go.microsoft.com/fwlink/?linkid=873065)                         | [What's new in ADK for Windows 10, version 1803](what-s-new-in-kits-and-tools.md#whats-new-in-the-windows-adk-for-windows-10-version-1803)                                                                                                                                                                      |
| [ADK for Windows 10, version 1709](https://go.microsoft.com/fwlink/p/?linkid=859206)                       | [What's new in ADK for Windows 10, version 1709](what-s-new-in-kits-and-tools.md#whats-new-in-the-windows-adk-for-windows-10-version-1709). <br>For IoT Core for Windows 10, version 1709, also [download the IoT Core Add-Ins v4.4](https://github.com/ms-iot/iot-adk-addonkit/releases/tag/v4.4).             |
| [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542)                       | [What's new in ADK for Windows 10, version 1703](what-s-new-in-kits-and-tools.md#whats-new-in-the-windows-adk-for-windows-10-version-1703). <br>For IoT Core for Windows 10, version 1703, also [download the IoT Core Add-Ins v3.2](https://github.com/ms-iot/iot-adk-addonkit/releases/tag/v3.2).             |
| [ADK for Windows 10, version 1607](https://go.microsoft.com/fwlink/p/?LinkId=526740)                       | [What's new in ADK for Windows 10, version 1607](what-s-new-in-kits-and-tools.md#whats-new-in-the-windows-adk-for-windows-10-version-1607).  <br>For IoT Core for Windows 10, version 1607, also [download the IoT Core Add-Ins v2.0 (14393_v1)](https://github.com/ms-iot/iot-adk-addonkit/releases/tag/v2.0). |
| [ADK for Windows 8](https://www.microsoft.com/download/details.aspx?id=30652)                              | [What's new in ADK for Windows 8](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-8.1-and-8/dn247001(v=win.10))                                                                                                                                                                             |
| [AIK for Windows 7](https://www.microsoft.com/download/details.aspx?id=5753)                               | [WAIK for Windows 7 Readme](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/dd349350(v=ws.10))                                                                                                                                                                                            |
| [Windows OEM HAL Extension Test Cert 2017](https://go.microsoft.com/fwlink/?linkid=872294)                 | To use the Windows ADK to work with HAL Extensions, download and install the updated Windows OEM HAL Extension Test Cert 2017 (TEST ONLY) certificate. [Learn more](https://support.microsoft.com/help/4131991).                                                                                                |

## Install the ADK

Install the ADK based on what works best for your environment.

* For computers that are connected to the internet, you can use any of the download links above.
* For secure manufacturing environments, you can [install the Windows ADK offline](adk-offline-install.md).
* For automated installs, you can [silently install the Windows ADK](adk-offline-install.md#install-the-windows-adk-on-an-offline-computer-using-the-command-line).

## Windows ADK tools for IT pros

Windows ADK contains core assessment and deployment tools that IT Pros can use to deploy Windows 10 company-wide, including the User State Migration Tool (USMT) and Volume Activation Management Tool (VAMT).

* [Learn more about VAMT](https://docs.microsoft.com/windows/deployment/volume-activation/volume-activation-management-tool)
* [Learn more about USMT](https://docs.microsoft.com/windows/deployment/usmt/usmt-technical-reference)
* [Learn more about Application Virtualization (App-V)](https://docs.microsoft.com/windows/application-management/app-v/appv-for-windows)
* [Learn more about IT Pro scenarios](https://docs.microsoft.com/windows/deployment/windows-adk-scenarios-for-it-pros)

## Related downloads

* [Download the Windows Driver Kit](https://developer.microsoft.com/windows/hardware/windows-driver-kit)
* [Download the Windows HLK, HCK, or Logo Kit](https://developer.microsoft.com/windows/hardware/windows-hardware-lab-kit)
* [Download the debugging tools for Windows (WinDbg)](https://developer.microsoft.com/windows/hardware/download-windbg)
* [Download the Windows Symbols Packages](https://developer.microsoft.com/windows/hardware/download-symbols)
* [Download Windows ADK Insider Preview builds](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)
