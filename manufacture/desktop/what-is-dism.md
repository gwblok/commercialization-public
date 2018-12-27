---

Description: 'DISM overview'
ms.assetid: ad08e68c-616f-404a-bfc6-c7bf1a4666f0
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'DISM Overview'

ms.date: 04/16/2018
ms.topic: article


---

# DISM Overview

## What's New in DISM


DISM in Windows 10 supports new features:

-   **Full Flash Update (.FFU)**: DISM supports the Full Flash Update (.FFU) format, which captures an applies an entire drive, including partition information. This can make deployment faster and easier. See [Windows full flash update images](deploy-windows-using-full-flash-update--ffu.md) for more info.

-   **Capabilities**: This new Windows package type allows you to request services like .NET or languages without specifying the version. Use DISM to search multiple sources like Windows Update or your corporate servers to find and install the latest version. For more info, see [Features on Demand](features-on-demand-v2--capabilities.md).

-   **Compress operating system and provisioning packages**: Save space on a Windows image by running the operating system and other system files from compressed files. This replaces the WIMBoot features from Windows 8.1. See `/Apply-Image /Compact` and `/Apply-CustomDataImage` in [DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md) for more info.

## What is DISM?


Deployment Image Servicing and Management (DISM.exe) is a command-line tool that can be used to service and prepare Windows images, including those used for [Windows PE](winpe-intro.md), [Windows Recovery Environment (Windows RE)](windows-recovery-environment--windows-re--technical-reference.md) and [Windows Setup](windows-setup-technical-reference.md). DISM can be used to service a Windows image (.wim) or a virtual hard disk (.vhd or .vhdx).

DISM comes built into Windows and is available through the command line or from Windows PowerShell. To learn more about using DISM with PowerShell, see [Deployment Imaging Servicing Management (DISM) Cmdlets in Windows PowerShell](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).

### <span id="BKMK_reqs"></span><span id="bkmk_reqs"></span><span id="BKMK_REQS"></span>Image Requirements


DISM can be used to mount and service a Windows image from a .wim file, .ffu file, .vhd file, or a .vhdx file and also to update a running operating system. It can be used with older Windows image files (.wim files). However, it cannot be used with Windows images that are more recent than the installed version of DISM.

For a complete technical description of WIM, see the [Windows Imaging File Format (WIM) white paper](http://go.microsoft.com/fwlink/?LinkId=92227).

DISM can be used to service Windows images starting with Windows 7, Windows Server 2008 R2, and their associated versions of [WinPE](winpe-intro.md) and [WinRE](windows-recovery-environment--windows-re--technical-reference.md). The commands and options that are available for servicing an image depend on which Windows operating system you are servicing, and whether the image is offline or a currently running operating system.
 
For a list of the supported platforms and architecture types, see [DISM Supported Platforms](dism-supported-platforms.md).

### <span id="BKMK_common"></span><span id="bkmk_common"></span><span id="BKMK_COMMON"></span>Common Servicing and Management Scenarios


Image servicing and management solutions fall into two main categories:

-   Managing the data or information included in the Windows image, such as enumerating or taking an inventory of the components, updates, drivers, or applications that are contained in an image, capturing or splitting an image, appending or deleting images within a .wim file, or mounting an image.
-   Servicing the image itself, including adding or removing driver packages and drivers, modifying language settings, enabling or disabling Windows features, and upgrading to a higher edition of Windows.

### <span id="BKMK_limitations"></span><span id="bkmk_limitations"></span><span id="BKMK_LIMITATIONS"></span>Limitations


**Version compatibility.** DISM can be used with target images of older Windows operating systems, but not with target images of operating systems that are more recent than the installed version of DISM. For example, DISM from Windows 10, version 1511 can service Windows 10, version 1511 and version 1507 but not version 1607. To learn more, see [DISM Supported Platforms](dism-supported-platforms.md).

**Remote installation.** Installing packages to a remote computer over a network is not supported. 

**Answer files.** When you specify an answer file (Unattend.xml) for an image, only the settings specified in the `offlineServicing` configuration pass are applied. All other settings in the answer file are ignored. You can only specify one answer file at a time. For more information, see [DISM Unattended Servicing Command-Line Options](dism-unattended-servicing-command-line-options.md)

**Use an answer file to ensure package dependencies.** Some packages require other packages to be installed first. Because of this dependency requirement, you should use an answer file if you are installing multiple packages. By applying an answer file by using DISM, multiple packages can be installed in the correct order. This is the preferred method for installing multiple packages.

**Package installation order.** Packages are installed in the order that they are listed in the command line. In the following example, 1.inf, 2.inf, and 3.inf will be installed in the order in which they are listed in the command line.

```
DISM.exe /image:"c:\images\Image1" /Add-Driver /ForceUnsigned /DriverName:"C:\Drivers\1.inf" /DriverName:"C:\Drivers\2.inf" /DriverName:"C:\Drivers\3.inf"
```

**Multiple servicing commands are not supported.** You can specify multiple drivers (1.inf, 2.inf) or packages, but you cannot specify multiple commands (such as **/Add-Driver** **/Remove-Driver** or **/Add-Driver** **/Add-Package**) on the same command line.

**Wildcards.** Wildcards are not supported in DISM command lines.


## Where is DISM?


Deployment Image Servicing and Management (DISM.exe) is a command-line tool that can be used to service a Windows image or to prepare a Windows Preinstallation Environment (Windows PE) image. For more information about DISM see [What is DISM?](what-is-dism.md)


### DISM in Windows 10

DISM comes with Windows 10, in the `c:\windows\system32` folder, but you can run DISM in the command prompt from any location. You have to be running from a Command Prompt as administrator to use use DISM.

### DISM in the ADK

If you are running an older version of Windows, or you need a different version of DISM on your PC, download and install the Windows Assessment and Deployment Kit (Windows ADK), see [Windows Assessment and Deployment Kit (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/p/?LinkId=526740).

DISM appears in the Windows ADK here: `C:\Program Files (x86)\Windows Kits\<version>\Assessment and Deployment Kit\Deployment Tools\<arch>\DISM`

where &lt;version&gt; can be **8.0**, **8.1**, or **10**, and &lt;arch&gt; can be **x86** or **amd64**.

If you need to copy and ADK version of DISM to a PC that does not have the ADK, see [Copy DISM to another computer](copy-dism-to-another-computer.md).

## <span id="related_topics"></span>Related topics


[DISM Reference (Deployment Image Servicing and Management)](dism-reference--deployment-image-servicing-and-management.md)

[Deployment Image Servicing and Management (DISM) Command-Line Options](deployment-image-servicing-and-management--dism--command-line-options.md)

[Device Drivers and Deployment Overview](device-drivers-and-deployment-overview.md)

[Language Packs](language-packs-and-windows-deployment.md)

[Understanding Servicing Strategies](understanding-servicing-strategies.md)

 
