---
title: Creating a DISM Application
description: Creating a DISM Application
ms.assetid: 9b75cfca-7931-4478-8cdc-21f18504f383

ms.date: 10/25/2017
ms.topic: article


---

# Creating a DISM Application


You can develop applications by using the DISM API on any computer where you have installed the Windows Assessment and Deployment Kit (Windows ADK).

**Setting up the development environment**

1.  Add the path to DismApi.lib as an additional dependency in the linker input properties of your project.

    By default, DismApi.lib is installed with the Windows ADK at C:\\Program Files (x86)\\Windows Kits\\8.0\\Assessment and Deployment Kit\\Deployment and Imaging Tools\\SDKs\\DismApi\\Lib\\.

2.  Add the path to DismApi.h to the resource properties of your project.

    By default, DismApi.h is installed with the Windows ADK at C:\\Program Files (x86)\\Windows Kits\\8.0\\Assessment and Deployment Kit\\Deployment and Imaging Tools\\SDKs\\DismApi\\Include\\.

3.  Include the DISM API header file, DismApi.h, in your code.

## <span id="Required_DISM_API_functions"></span><span id="required_dism_api_functions"></span><span id="REQUIRED_DISM_API_FUNCTIONS"></span>Required DISM API functions


All DISM API processes must start with the [DismInitialize Function](disminitialize-function.md) before any other calls to the DISM API can be made. Conversely, the [DismShutdown Function](dismshutdown-function.md) is used to end a process.

To service an offline image, use the [DismMountImage Function](dismmountimage-function.md) to map the contents of the image to a directory on your local computer before opening a DISM session.

You can associate an offline or online Windows image with a [DISMSession](dismsession.md) by calling the [DismOpenSession Function](dismopensession-function.md). All servicing and repair operations on images are performed by using a DISMSession. All APIs that operate on an image accept a DismSession as their first parameter. You can call the [DismCloseSession Function](dismclosesession-function.md) to release a DismSession and then call the [DismUnmountImage Function](dismunmountimage-function.md) if you are finished using the offline image.

Some operations do not require a DISM session. These include the [DismGetImageInfo Function](dismgetimageinfo-function.md), [DismGetMountedImageInfo Function](dismgetmountedimageinfo-function.md), [DismRemountImage Function](dismremountimage-function.md), [DismCleanupMountpoints Function](dismcleanupmountpoints-function.md), [DismGetLastErrorMessage Function](dismgetlasterrormessage-function.md), and [DismDelete Function](dismdelete-function.md). These operations can be used at any point after the [DismInitialize Function](disminitialize-function.md) has been called.

For an example of a basic DISM application, see [DISM API Samples](dism-api-samples.md).

**Use paired DISM APIs to open and close processes**

1.  To start a DISM process, call the [DismInitialize Function](disminitialize-function.md).

2.  If you are using an offline image, call the [DismMountImage Function](dismmountimage-function.md).

3.  You can call any functions that do not require a DISM session, such as [DismGetMountedImageInfo Function](dismgetmountedimageinfo-function.md), after you have started the process with the DismInitialize function.

4.  If you want to service an image, first associate an offline or online Windows image with a [DISMSession](dismsession.md) by calling the [DismOpenSession Function](dismopensession-function.md).

5.  You can now perform any image management or servicing operations that use a DISM session, such as the [DismAddPackage Function](dismaddpackage-function.md).

    For more information about available functions, see [DISM API Functions](dism-api-functions.md).

6.  Save your changes by using the [DismCommitImage Function](dismcommitimage-function.md).

7.  If you have any open sessions, use the [DismCloseSession Function](dismclosesession-function.md) for each one to release the session and free the allocated memory.

8.  If you are finished using an offline image, call the [DismUnmountImage Function](dismunmountimage-function.md) to remove the mounted image from your local computer.

9.  To close the process, use the [DismShutdown Function](dismshutdown-function.md).

## <span id="related_topics"></span>Related topics


[DISM API Samples](dism-api-samples.md)

 

 




