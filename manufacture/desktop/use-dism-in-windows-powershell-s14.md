---

Description: Use DISM in Windows PowerShell
ms.assetid: c258fead-059f-4a03-b6af-24cdc7451ca3
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Use DISM in Windows PowerShell

ms.date: 05/02/2017
ms.topic: article


---

# Use DISM in Windows PowerShell


The Deployment Image Servicing and Management (DISM) cmdlets can be used to perform the same functions as the DISM.exe command-line tool. In many cases, the DISM cmdlet names are similar to their corresponding [Dism.exe options](deployment-image-servicing-and-management--dism--command-line-options.md) and the same arguments can be used. See [DISM PowerShell](https://docs.microsoft.com/powershell/module/dism/?view=win10-ps) for detailed information about the PowerShell cmdlets.   

## DISM command to DISM cmdlet mapping table

DISM cmdlet names don't always correspond directly to Dism.exe options. Here is a table that maps DISM commands to their corresponding PowerShell cmdlets.


|                   Dism.exe command                    |                                                                 DISM cmdlet                                                                 |
|-------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|               Dism.exe /Add-Capability                |            [Add-WindowsCapability](https://docs.microsoft.com/en-us/powershell/module/dism/add-windowscapability?view=win10-ps)             |
|                Dism.exe /Append-Image                 |                 [Add-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/add-windowsimage?view=win10-ps)                  |
|                 Dism.exe /Apply-Image                 |              [Expand-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/expand-windowsimage?view=win10-ps)               |
|                Dism.exe /Capture-Image                |                 [New-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/new-windowsimage?view=win10-ps)                  |
|             Dism.exe /Cleanup-MountPoints             |   [Clear-WindowsCorruptMountPoint](https://docs.microsoft.com/en-us/powershell/module/dism/clear-windowscorruptmountpoint?view=win10-ps)    |
|                Dism.exe /Commit-Image                 |                [Save-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/save-windowsimage?view=win10-ps)                 |
|                Dism.exe /Export-Image                 |              [Export-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/export-windowsimage?view=win10-ps)               |
|              Dism.exe /Get-Capabilities               |            [Get-WindowsCapability](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowscapability?view=win10-ps)             |
|                Dism.exe /Get-ImageInfo                |                 [Get-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsimage?view=win10-ps)                  |
|            Dism.exe /Get-MountedImageInfo             |             [Get-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsimage?view=win10-ps) -Mounted             |
|              Dism.exe /Get-WimBootEntry               |                 [Get-WIMBootEntry](https://docs.microsoft.com/en-us/powershell/module/dism/get-wimbootentry?view=win10-ps)                  |
|                 Dism.exe /List-Image                  |          [Get-WindowsImageContent](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsimagecontent?view=win10-ps)           |
|                 Dism.exe /Mount-Image                 |               [Mount-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/mount-windowsimage?view=win10-ps)                |
|                 Dism.exe /Split-Image                 |               [Split-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/split-windowsimage?view=win10-ps)                |
|              Dism.exe /Remove-Capability              |         [Remove-WindowsCapability](https://docs.microsoft.com/en-us/powershell/module/dism/remove-windowscapability?view=win10-ps)          |
|                Dism.exe /Remove-Image                 |              [Remove-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/remove-windowsimage?view=win10-ps)               |
|                Dism.exe /Remount-Image                |           [Mount-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/mount-windowsimage?view=win10-ps) -Remount           |
|                Dism.exe /Unmount-Image                |            [Dismount-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/dismount-windowsimage?view=win10-ps)             |
|             Dism.exe /Update-WimBootEntry             |              [Update-WIMBootEntry](https://docs.microsoft.com/en-us/powershell/module/dism/update-wimbootentry?view=win10-ps)               |
|          Dism.exe /Image:\<...> /Add-Driver           |                [Add-WindowsDriver](https://docs.microsoft.com/en-us/powershell/module/dism/add-windowsdriver?view=win10-ps)                 |
|          Dism.exe /Image:\<...> /Add-Package          |               [Add-WindowsPackage](https://docs.microsoft.com/en-us/powershell/module/dism/add-windowspackage?view=win10-ps)                |
|  Dism.exe /Image:\<...> /Add-ProvisionedAppxPackage   |       [Add-AppxProvisionedPackage](https://docs.microsoft.com/en-us/powershell/module/dism/Add-AppxProvisionedPackage?view=win10-ps)        |
|  Dism.exe /Image:\<...> /Cleanup-Image /CheckHealth   |        [Repair-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/repair-windowsimage?view=win10-ps) -CheckHealth        |
|   Dism.exe /Image:\<...> /Cleanup-Image /ScanHealth   |        [Repair-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/repair-windowsimage?view=win10-ps) -ScanHealth         |
| Dism.exe /Image:\<...> /Cleanup-Image /RestoreHealth  |       [Repair-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/repair-windowsimage?view=win10-ps) -RestoreHealth       |
|        Dism.exe /Image:\<...> /Disable-Feature        |   [Disable-WindowsOptionalFeature](https://docs.microsoft.com/en-us/powershell/module/dism/disable-windowsoptionalfeature?view=win10-ps)    |
|        Dism.exe /Image:\<...> /Enable-Feature         |    [Enable-WindowsOptionalFeature](https://docs.microsoft.com/en-us/powershell/module/dism/enable-windowsoptionalfeature?view=win10-ps)     |
|         Dism.exe /Image:\<...> /Export-Driver         |             [Export-WindowsDriver](https://docs.microsoft.com/en-us/powershell/module/dism/export-windowsdriver?view=win10-ps)              |
|      Dism.exe /Image:\<...> /Get-CurrentEdition       |           [Get-WindowsEdition](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsedition?view=win10-ps) -Current           |
|        Dism.exe /Image:\<...> /Get-Driverinfo         |            [Get-WindowsDriver](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsdriver?view=win10-ps) -Driver             |
|          Dism.exe /Image:\<...> /Get-Drivers          |                [Get-WindowsDriver](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsdriver?view=win10-ps)                 |
|        Dism.exe /Image:\<...> /Get-Featureinfo        | [Get-WindowsOptionalFeature](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsoptionalfeature?view=win10-ps) -FeatureName |
|         Dism.exe /Image:\<...> /Get-Features          |       [Get-WindowsOptionalFeature](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsoptionalfeature?view=win10-ps)        |
|        Dism.exe /Image:\<...> /Get-Packageinfo        |         [Get-WindowsPackage](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowspackage?view=win10-ps) -PackagePath         |
|         Dism.exe /Image:\<...> /Get-Packages          |               [Get-WindowsPackage](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowspackage?view=win10-ps)                |
|  Dism.exe /Image:\<...> /Get-ProvisionedAppxPackages  |       [Get-AppxProvisionedPackage](https://docs.microsoft.com/en-us/powershell/module/dism/get-appxprovisionedpackage?view=win10-ps)        |
|      Dism.exe /Image:\<...> /Get-TargetEditions       |           [Get-WindowsEdition](https://docs.microsoft.com/en-us/powershell/module/dism/get-windowsedition?view=win10-ps) -Target            |
|        Dism.exe /Image:\<...> /Optimize-Image         |            [Optimize-WindowsImage](https://docs.microsoft.com/en-us/powershell/module/dism/optimize-windowsimage?view=win10-ps)             |
|         Dism.exe /Image:\<...> /Remove-Driver         |             [Remove-WindowsDriver](https://docs.microsoft.com/en-us/powershell/module/dism/remove-windowsdriver?view=win10-ps)              |
|        Dism.exe /Image:\<...> /Remove-Package         |            [Remove-WindowsPackage](https://docs.microsoft.com/en-us/powershell/module/dism/remove-windowspackage?view=win10-ps)             |
| Dism.exe /Image:\<...> /Remove-ProvisionedAppxPackage |    [Remove-AppxProvisionedPackage](https://docs.microsoft.com/en-us/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps)     |
|          Dism.exe /Image:\<...> /Set-Edition          |               [Set-WindowsEdition](https://docs.microsoft.com/en-us/powershell/module/dism/set-windowsedition?view=win10-ps)                |
|        Dism.exe /Image:\<...> /Set-ProductKey         |            [Set-WindowsProductKey](https://docs.microsoft.com/en-us/powershell/module/dism/set-windowsproductkey?view=win10-ps)             |
|  Dism.exe /Image:\<...> /Set-ProvisionedAppxDataFile  |      [Set-AppXProvisionedDataFile](https://docs.microsoft.com/en-us/powershell/module/dism/set-appxprovisioneddatafile?view=win10-ps)       |

## Use DISM Powershell modules in WinPE

You can add Powershell support to WinPE. Visit [Adding PowerShell support to Windows PE](winpe-adding-powershell-support-to-windows-pe.md) to learn how.

## Use DISM PowerShell modules in previous versions of Windows

The DISM PowerShell module is included in Windows 10 and Windows Server 2016. On other supported operating systems, you can install the Windows Assessment and Deployment Kit (ADK) which includes the DISM PowerShell module. See [the previous version of this topic for more information](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-8.1-and-8/hh825010(v%3dwin.10)#install-the-windows-assessment-and-deployment-kit-optional).



## <span id="related_topics"></span>Related topics


[DISM - Deployment Image Servicing and Management Technical Reference for Windows](dism---deployment-image-servicing-and-management-technical-reference-for-windows.md)

[DISM Supported Platforms](dism-supported-platforms.md)










