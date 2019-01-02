---
title: DISM API Package and Feature Functions Sample
description: DISM API Package and Feature Functions Sample
ms.assetid: f5b04100-350d-43c3-8d1f-a2bcdfd19890

ms.date: 10/25/2017
ms.topic: article


---

# DISM API Package and Feature Functions Sample


The Deployment Image Servicing and Management (DISM) API allows you to build customized solutions on the DISM platform. You can use the DISM API to install, uninstall, configure, and update Windows features, packages, and drivers in a Windows image.

## <span id="Sample_Using_Feature_Functions"></span><span id="sample_using_feature_functions"></span><span id="SAMPLE_USING_FEATURE_FUNCTIONS"></span>Sample Using Feature Functions


This example shows how to mount a VHD, get image info, get packages, get package info, add a package, get features, and to commit while unmounting.

``` syntax
#include "windows.h"
#include <stdio.h>
#include "DismApi.h"

int _cdecl wmain()
{
    HRESULT hr = S_OK;
    HRESULT hrLocal = S_OK;
    DismSession session = DISM_SESSION_DEFAULT;
    BOOL bMounted = FALSE; 
    DWORD dwUnmountFlags = DISM_DISCARD_IMAGE; 
    DismImageInfo *pImageInfo = NULL; 
    DismPackage *pPackage = NULL; 
    DismPackageInfo *pPackageInfo = NULL; 
    DismFeature *pFeatures = NULL; 
    UINT uiCount = 0; 

    // Initialize the API
    hr = DismInitialize(DismLogErrorsWarningsInfo, L"C:\\MyLogFile.txt", NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismInitialize Failed: %x\n", hr); 
        goto Cleanup; 
    }

    wprintf(L"Mounting: ");

    // Mount a VHD image 
    hr = DismMountImage(L"C:\\Install.VHD",
                        L"C:\\MountPath",
                        1, 
                        NULL, 
                        DismImageIndex, 
                        DISM_MOUNT_READWRITE, 
                        NULL, 
                        NULL, 
                        NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"\nDismMountImage Failed: %x\n", hr); 
        goto Cleanup; 
    }

    bMounted = TRUE; 
    wprintf(L"Complete.\n\n");

    // Get some information about the image that was mounted
    hr = DismGetImageInfo(L"C:\\Install.VHD",
                          &pImageInfo, 
                          &uiCount); 
    if( FAILED(hr)) 
    {
        wprintf(L"\nDismGetImageInfo Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // Print out some information from the image
    wprintf(L"\n\nHere is some information about this image:\n\n");
    for (UINT i = 0; i < uiCount; ++i) 
    {
        wprintf(L"Image index: %u\n", i); 
        wprintf(L"OS Version: %u.%u.%u.%u\n", pImageInfo[i].MajorVersion, pImageInfo[i].MinorVersion, pImageInfo[i].Build, pImageInfo[i].SpBuild); 
        wprintf(L"Architecture: %u\n\n", pImageInfo[i].Architecture); 
    }

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

    // Get a list of all of the packages installed in the image
    hr = DismGetPackages(session, 
                         &pPackage, 
                         &uiCount); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismGetPackages Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // If there is at least one package, then get some extended information
    // about that package
    if (uiCount > 0) 
    {
        wprintf(L"Found %u packages: %u\n", uiCount); 
        wprintf(L"Getting more detailed information about the first package\n\n");
        hr = DismGetPackageInfo(session, 
                                pPackage[0].PackageName, 
                                DismPackageName, 
                                &pPackageInfo); 
        if( FAILED(hr)) 
        {
            wprintf(L"DismGetPackageInfo Failed: %x\n", hr); 
            goto Cleanup; 
        }

        wprintf(L"Package Install time:\n");
        wprintf(L"Year:%u\n", pPackageInfo->InstallTime.wYear); 
        wprintf(L"Month:%u\n", pPackageInfo->InstallTime.wMonth); 
        wprintf(L"Day:%u\n", pPackageInfo->InstallTime.wDay); 
    }

    // Add a package (this could be a hotfix) 
    hr = DismAddPackage(session, 
                        L"c:\\AddressBook.cab", 
                        FALSE, 
                        FALSE, 
                        NULL, 
                        NULL, 
                        NULL); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismAddPackage Failed: %x\n", hr); 
        goto Cleanup; 
    }

    // If the package was successfully added, then commit the image later when
    // it is unmounted
    dwUnmountFlags = DISM_COMMIT_IMAGE; 

    // Get a list of all of the features in the image
    hr = DismGetFeatures(session, 
                         NULL, 
                         DismPackageNone, 
                         &pFeatures, 
                         &uiCount); 
    if( FAILED(hr)) 
    {
        wprintf(L"DismGetFeatures Failed: %x\n", hr); 
        goto Cleanup; 
    }

    //Print out all of the feature names in the image
    wprintf(L"\n\nHere are all of the features in the image:\n\n");
    for (UINT i = 0; i < uiCount; ++i) 
    {
        wprintf(L"Feature name: %s\n", pFeatures[i].FeatureName); 
    }

Cleanup: 

    // Delete the memory associated with the objects that were returned
    hrLocal = DismDelete(pImageInfo); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    hrLocal = DismDelete(pPackage); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    hrLocal = DismDelete(pPackageInfo); 
    if( FAILED(hrLocal)) 
    {
        wprintf(L"DismDelete Failed: %x\n", hrLocal); 
    }

    hrLocal = DismDelete(pFeatures); 
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

    // Unmount the image if it is mounted.  If the package was added successfully,
    //then commit the changes.  Otherwise, discard the
    // changes
    if (bMounted) 
    {
        hrLocal = DismUnmountImage(L"C:\\MountPath",
                                   dwUnmountFlags, 
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

 

 




