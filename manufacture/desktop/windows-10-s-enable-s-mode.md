---

Description: 'Enable S mode'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Enable S mode'

ms.date: 04/18/2018
ms.topic: article
ms.custom: RS5
---

# Enable S mode

This topic shows how to add S mode to a supported Windows 10 edition. The following information only applies to Windows 10, version 1803 or later. 

## Overview

Beginning with Windows 10, version 1803, you can enable S mode on supported editions. This is a change from previous versions of Windows where Windows 10 S was its own edition with its own base media. To enable S mode, you'll create an unattend file, and then use DISM to apply the unattend file to a mounted Windows image.

We recommend enabling S mode and adding your manufacturing key at the same time. We show you how to do this in the [Windows 10 in S Mode deployment lab](windows-10-s-deployment-sxs.md), as well as in the [OEM deployment of Windows 10 for desktop editions](oem-deployment-of-windows-10-for-desktop-editions.md) lab.


## Enable S Mode

To enable S mode in a Windows image, use an Unattend file that has a setting in Pass 2 - offlineServicing, and use DISM to apply it to our mounted Windows image.

1.  Mount your Windows image.
2.  Use Windows SIM to create or modify an unattend file.
3.  Add the amd64_Microsoft_Windows_CodeIntegrity component to Pass 2 offline Servicing.
4.  Set amd64_Microsoft_Windows_CodeIntegrity\SkuPolicyRequired to 1. The offline servicing pass in your unattend.xml file should look like this:
    
    ``` XML
        <settings pass="offlineServicing">
        <component name="Microsoft-Windows-CodeIntegrity" 
                    processorArchitecture="amd64" 
                    publicKeyToken="31bf3856ad364e35" 
                    language="neutral" 
                    versionScope="nonSxS" 
                    xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" 
                    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <SkuPolicyRequired>1</SkuPolicyRequired>
        </component>
        </settings>
    ```

5.  Save the answer file in the `Windows\Panther` folder of your mounted image as unattend.xml.
6.  Use DISM to apply the unattend file and enable S Mode:

    ```
    dism /image:C:\mount\windows /apply-unattend:C:\mount\windows\windows\panther\unattend.xml
    ```

    > Note: Only Pass 2 - offline Servicing is processed when an unattend file is applied with DISM.

S mode is now applied to the Windows image. When the PC boots, the same Code Integrity policy that is enforced in Windows 10 S will be enforced on your Windows installation. If you are going to boot the PC into Audit Mode, you'll have to enable manufacturing mode. [Enable manufacturing mode](windows-10-s-manufacturing-mode.md) describes how to do that.
