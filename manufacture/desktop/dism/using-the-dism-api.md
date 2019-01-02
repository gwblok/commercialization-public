---
title: Using the DISM API
description: Using the DISM API
ms.assetid: 56c089b7-d1d4-4452-a31d-610ce3f96d75

ms.date: 10/25/2017
ms.topic: article


---

# Using the DISM API


The Deployment Image Servicing and Management (DISM) API allows you to build customized solutions on the DISM platform. You can use the DISM API to install, uninstall, configure, and update Windows features, packages, and drivers in a Windows image. DISM can be used to manage and service Windows images in either the Windows image (.wim) file format or virtual hard drive (.vhd, .vhdx) files.

In this section:

[Requirements](#bkmk-requirements)

[Supported Target Images](#bkmk-target)

[Best Practices](#bkmk-best)

[Other DISM Tools](#bkmk-other)

## <span id="BKMK_Requirements"></span><span id="bkmk_requirements"></span><span id="BKMK_REQUIREMENTS"></span>Requirements


You must install the Windows Assessment and Deployment Kit (Windows ADK) on your development computer in order to create DISM API applications:

-   Your customized solutions on the DISM platform are developed using the DISM SDK. This is installed when the Windows ADK is installed. For more information about supported operating systems, see the [Windows Assessment and Deployment Kit (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/p/?LinkId=206587).

-   When running customized solutions on the DISM platform, you must verify that the Windows ADK architecture version matches the operating system architecture version. For example, a customized solution developed for 32-bit PCs runs on the 32-bit version of Windows.

-   In order to properly develop and run your customized solutions on the DISM platform, you must verify you are using the DISM binaries from the Windows ADK:

    -   Install the latest version of the Windows ADK on the PC that will run the customized solution.

    -   The binary files for your customized solutions must be saved in the same directory as the DISM binaries installed by the Windows ADK. For example, if you are running Windows 8 (x64) and the Windows ADK for Windows 8.1, your customized solutions binaries must be located in **c:\\Program Files (x86)\\Windows Kits\\8.1\\Assessment and Deployment Kit\\Deployment Tools\\amd64\\DISM**.

    -   Run your customized solutions from the **Deployment and Imaging Tools Environment** so that the necessary environment variables are set up prior running your solutions.

        From the start screen, type deployment. Right-click **Deployment and Imaging Tools Environment** and select **Run as administrator**.

        **Note**  
        If you don’t run from the **Deployment and Imaging Tools Environment**, you must verify that the PATH environment variable uses the location of the DISM binaries from the Windows ADK.

         

-   You will need a supported Windows image file type, .wim, .vhd, or .vhdx, or an online installation of Windows to use the DISMAPI for servicing and management. Some operations are not valid on online images. For more information, see the [DISM API Reference](dism-api-reference.md).

## <span id="BKMK_Target"></span><span id="bkmk_target"></span><span id="BKMK_TARGET"></span>Supported Target Images


The Windows image file that you are servicing on your host computer can be a .wim file, a .vhd or .vhdx file, or an online installation of Windows. Additionally, cross-architecture servicing is supported. You can service an x64 image from an x86 system or an x64 system. You can service an x86 image from an x64 system or an x86 system.

All DISMAPI functions can be performed on Windows 8 and Windows Server® 2012 target images. To see if a function can be performed on other target images, see the Requirements section of the function reference topic in the [DISM API Reference](dism-api-reference.md).

## <span id="BKMK_Best"></span><span id="bkmk_best"></span><span id="BKMK_BEST"></span>Best Practices


**Memory management.** Certain DISM API functions return structures or arrays of structures. These structures are returned to the user as a pointer to an object on the heap. The heap memory is allocated by the DISM API. The client must call the [DismDelete Function](dismdelete-function.md) to ensure that this memory is released.

**Mounting a VHD with the DiskPart tool.** When possible, you should use the DISM API to mount and unmount images you want to service within the DISM framework. Using another tool, such as the DiskPart tool, to mount and unmount the image can have unexpected effects.

**File paths.** All paths accepted by DISM API functions can be relative or absolute. As a best practice, limit the length of file paths. File paths that are too long or exceed the maximum length limitation for Windows will cause failures in DISM.

**Matching calls to open and close sessions.** Always release a DISM Session by using the [DismCloseSession Function](dismclosesession-function.md) before calling the [DismShutdown Function](dismshutdown-function.md). You can also unmount the image with the [DismUnmountImage Function](dismunmountimage-function.md) after closing the session and before calling the DismShutdown Function.

## <span id="BKMK_Other"></span><span id="bkmk_other"></span><span id="BKMK_OTHER"></span>Other DISM tools


For more information about the DISM platform and other ways to access the servicing and management functionality, see the [DISM Technical Reference](http://go.microsoft.com/fwlink/?LinkId=200687) in the Windows® Assessment and Deployment Kit (Windows ADK) Technical Reference. You can also use the DISM.exe tool in the Windows ADK to capture an image as a .wim file.

## <span id="related_topics"></span>Related topics


[Creating a DISM Application](creating-a-dism-application.md)

[DISM API Troubleshooting](dism-api-troubleshooting.md)

[DISM API Reference](dism-api-reference.md)

[DISM API Samples](dism-api-samples.md)

 

 




