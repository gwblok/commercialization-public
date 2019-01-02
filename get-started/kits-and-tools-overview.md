---
title: Kits and tools overview
description: An overview of the kits and tools needed for developing with Windows 10 Mobile and Windows 10.
ms.assetid: F0055AF7-D679-4BC6-94C8-2FCD5832B9D8
ms.date: 05/02/2017
ms.topic: article


---
# Kits and tools overview

These kits and tools are available for use with Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) and Windows 10 Mobile for development and manufacturing.

Learn about known issues and workarounds for this release in our [WinHEC forums](http://go.microsoft.com/fwlink/p/?LinkId=526372).

## ADK for Windows 10

[Download the ADK for Windows 10](adk-install.md)

Download the Windows ADK to install tools and documentation for OEMs and ODMs to customize Windows 10 images, assess the quality and performance of systems or components, and to deploy Windows operating systems to new computers. The Windows ADK includes Windows Configuration Designer, the Windows Assessment Toolkit, the Windows Performance Toolkit, and several new and improved deployment tools that can help you automate a large-scale deployment of Windows 10. For more information, see [What’s new in kits and tools](what-s-new-in-kits-and-tools.md).

### Learn about the ADK tools

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

## Microsoft Visual Studio 2017

[Install Microsoft Visual Studio 2017](https://www.visualstudio.com/vs/)

Start by downloading Visual Studio 2017 and Microsoft Visual Studio Tools for Windows 10. Used together, Microsoft Visual Studio, Visual Studio Tools for Windows 10, standalone Windows Software Development Kit (SDK) for Windows 10, and Windows Driver Kit (WDK) 10 provide an integrated development environment for creating efficient, high-quality drivers for devices running Windows 10.

## Standalone Windows SDK for Windows 10

[Install the Standalone Windows SDK for Windows 10](https://go.microsoft.com/fwlink/p/?LinkID=845298)

Windows SDK for Windows 10 contains headers, libraries, and tools you can use when you create apps that run on Windows operating systems. You can use the Windows SDK for Windows 10, along with your chosen development environment, to write apps for Windows 10 for desktop editions and Windows 10 Mobile.

## WDK 10

[Install the Windows Driver Kit (WDK) 10](https://developer.microsoft.com/windows/hardware/windows-driver-kit)

[Download Universal Windows driver samples](http://go.microsoft.com/fwlink/p/?LinkId=526735)

WDK 10 contains the tools to build, test, debug, and deploy drivers for Windows 10. WDK 10 unifies support for mobile and desktop devices, Universal Windows drivers, and, with Visual Studio, provides a unified test experience with reliable deployment and debug provisioning that includes WinDbg. You can run many basic certification tests in the integrated environment. The WDK 10 includes templates for several technologies and driver models, including Windows Driver Frameworks (WDF), Universal Serial Bus (USB), print, networking, and file system filters. WDK 10 also supports Windows 7, Windows 8, and Windows 8.1 driver development.

For more information about driver development for Windows 10, see [What's new in Universal Windows driver development](https://msdn.microsoft.com/windows/hardware/drivers/what-s-new-in-driver-development) and [What's new in kits and tools](what-s-new-in-kits-and-tools.md).

## Enterprise WDK (EWDK)

The Enterprise WDK (EWDK) is a kit that large organizations can use as an alternative to downloading and installing the SDK and WDK individually on each computer. The EWDK has a command-line build environment that is based on files and is not computer-dependent, so after the environment file structure has been created, it can be distributed for direct use, such as through version control software or by zipping the contents and unzipping on other computers. It contains the necessary elements to build *Windows Driver Model* (WDM) drivers, WDF drivers, and classic Windows test applications.

## Windows symbols

Symbol files make it easier to debug your code. The easiest way to get Windows symbols is to use the [Microsoft Symbol Server](http://support.microsoft.com/kb/311503/). If you prefer to download the entire set of symbols for a particular version of Windows, [download a symbol package](http://go.microsoft.com/fwlink/?LinkId=528570).

## Windows Hardware Lab Kit (HLK) for Windows 10

[Download the HLK for Windows 10](http://go.microsoft.com/fwlink/p/?LinkId=532718)

The Windows Hardware Lab Kit (HLK) for Windows 10 is an all-purpose test and measurement kit to help you determine how well your hardware interacts with Windows. The HLK provides a test infrastructure for PCs. For more information on the using the HLK with Windows 10, see [Windows Hardware Lab Kit User's Guide](https://msdn.microsoft.com/library/windows/hardware/dn939963.aspx).

## HLK supplemental test content

Some tests, like graphics and multimedia tests, require additional files for testing. You can find this content in the **Windows HLK supplemental media test content** section on the [Download the Windows HLK, HCK, or Logo Kit](http://go.microsoft.com/fwlink/p/?LinkId=532718) page.

## What else is new?

See [What's new in kits and tools](what-s-new-in-kits-and-tools.md)
