---
title: DISM API Driver Functions Sample
description: DISM API Driver Functions Sample
ms.assetid: 34d6a3e4-240b-4b68-b8d6-48cb6678482d

ms.date: 10/25/2017
ms.topic: article


---

# DISM API Driver Functions Sample


The Deployment Image Servicing and Management (DISM) API allows you to build customized solutions on the DISM platform. You can use the DISM API to install, uninstall, configure, and update Windows features, packages, and drivers in a Windows image.

## <span id="Sample_Using_Driver_Functions"></span><span id="sample_using_driver_functions"></span><span id="SAMPLE_USING_DRIVER_FUNCTIONS"></span>Sample Using Driver Functions


This example shows how to mount, commit, and unmount a WIM image, use progress callback, get and enumerate drivers, and open and close a session.

``` syntax
#include "windows.h"
#include <stdio.h>
#include "DismApi.h"

void MountProgressCallback(
    __in UINT uiCurrent, 
    __in UINT uiTotal, 
    __in PVOID pUserData
    ) 
{
    UNREFERENCED_PARAMETER(pUserData); 

    wprintf(L".");

    if (uiCurrent == uiTotal) 
    {
        wprintf(L"\nMounting Complete\n");
    }
}

int _cdecl wmain()
{
    HRESULT hr = S_OK; 
    HRESULT hrLocal = S_OK; 
    DismSession session = DISM_SESSION_DEFAULT; 
    BOOL bMounted = FALSE; 
    UINT uiCount = 0; 
    DismDriverPackage *driverPackage = NULL; 
    DismDriverPackage *driverPackage2 = NULL; 
    DismDriver *driversInDriverPackage = NULL; 

    // Initialize the API
    hr = DismInitialize(DismLogErrorsWarningsInfo, L"C:\\MyLogFile.txt", NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismInitialize Failed: %x\n", hr); 
        goto Cleanup; 
    }

    wprintf(L"Mounting: ");

    // Mount a WIM image 
    hr = DismMountImage(L"C:\\install.wim",
                        L"C:\\MountPath",
                        1, 
                        NULL, 
                        DismImageIndex, 
                        DISM_MOUNT_READWRITE, 
                        NULL, 
                        MountProgressCallback, 
                        NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"\nDismMountImage Failed: %x\n", hr); 
        goto Cleanup; 
    }

    bMounted = TRUE; 

    // Open a session against the mounted image
    hr = DismOpenSession(L"C:\\MountPath",
                         NULL, 
                         NULL, 
                         &session); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismOpenSession Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // Add a driver into the mounted image
    hr = DismAddDriver(session, 
                       L"C:\\drivers\\MyDriver.inf", 
                       FALSE ); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismAddDriver Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // Get the list of drivers in the mounted image
    hr = DismGetDrivers(session, 
                        FALSE, 
                        &driverPackage, 
                        &uiCount ); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismGetDrivers Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // Print out the names of all of the drivers from the mounted image
    wprintf(L"\n\nThese are the third party drivers from the image:\n\n");
    for (UINT i = 0; i < uiCount; ++i) 
    {
        wprintf(L"Driver Package %u: %s\n", i, driverPackage[i].PublishedName); 
        wprintf(L"Original file name: %s\n\n", driverPackage[i].OriginalFileName); 
    }

    // Get more extended information about the first driver from the mounted
    // image.  Note that the third party drivers are always named as oem%d.inf
    hr = DismGetDriverInfo(session, 
                           L"oem0.inf", 
                           &driversInDriverPackage, 
                           &uiCount, 
                           &driverPackage2); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismGetDriverInfo Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // Print out the top level info for this driver
    wprintf(L"\n\nThis is more detailed information about the first driver package and the set of drivers contained inside\n\n");
    wprintf(L"Driver Package: %s\n", driverPackage->PublishedName); 
    wprintf(L"Original file name: %s\n\n", driverPackage->OriginalFileName); 

    // Print out some specific information for each driver in the driver package
    for (UINT i = 0; i < uiCount; ++i) 
    {
        wprintf(L"Driver %u: %s\n", i, driversInDriverPackage[i].ManufacturerName); 
        wprintf(L"Hardware Description: %s\n", driversInDriverPackage[i].HardwareDescription); 
        wprintf(L"Hardware Id: %s\n", driversInDriverPackage[i].HardwareId); 
        wprintf(L"Architecture: %u\n", driversInDriverPackage[i].Architecture); 
        wprintf(L"Service Name: %s\n", driversInDriverPackage[i].ServiceName); 
        wprintf(L"Compatible Ids: %s\n", driversInDriverPackage[i].CompatibleIds); 
        wprintf(L"Exclude Ids: %s\n\n", driversInDriverPackage[i].ExcludeIds); 
    }

    // Commit the changes that were made to the image
    hr = DismCommitImage(session, 
                         0, 
                         NULL, 
                         NULL, 
                         NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismCommitImage failed: %x\n", hr); 
        goto Cleanup; 
    }

Cleanup: 

    // Delete the memory associated with the objects that were returned
    hrLocal = DismDelete(driverPackage); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    hrLocal = DismDelete(driverPackage2); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    hrLocal = DismDelete(driversInDriverPackage); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    // Close the DismSession to free up resources tied to this image servicing session
    hrLocal = DismCloseSession (session); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismCloseSession Failed: %x\n", hrLocal); 
    }

    // Unmount the image if is wa mounted
    if (bMounted) 
    {
        hrLocal = DismUnmountImage(L"C:\\MountPath",
                                   DISM_DISCARD_IMAGE, 
                                   NULL, 
                                   NULL, 
                                   NULL); 
        if( FAILED(hrLocal)) 
        {
            wprintf(L"DismUnmountImage Failed: %x\n", hrLocal); 
        }
    }

    // Shutdown the DISM API to free up remaining resources
    hrLocal = DismShutdown();
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismShutdown Failed: %x\n", hr); 
    }

    wprintf(L"Return code is: %x\n", hr); 
    return hr; 
}
```

## <span id="related_topics"></span>Related topics


[DISM API Samples](dism-api-samples.md)

[DISM API Reference](dism-api-reference.md)

[Using the DISM API](using-the-dism-api.md)

[Creating a DISM Application](creating-a-dism-application.md)

[DISM API Troubleshooting](dism-api-troubleshooting.md)

 

 




