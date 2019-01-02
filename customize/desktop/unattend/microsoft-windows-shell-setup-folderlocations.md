---
title: FolderLocations
description: FolderLocations
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f5b30062-eba6-4a3f-b635-4f33828b1107
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FolderLocations

The `FolderLocations` setting specifies the location of the user-profile and program-data folders.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ProfilesDirectory](microsoft-windows-shell-setup-folderlocations-profilesdirectory.md) | Specifies the path to the user profile folder. |
| [ProgramData](microsoft-windows-shell-setup-folderlocations-programdata.md) | Specifies the path to the program-data folder. |

> [!Warning]
> Use this setting only in a test environment. If you change the default location of the program-data folders to a volume other than the system volume, you cannot service your image. Any updates, fixes, or service packs may not be applied to the installation.

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **FolderLocations**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML example shows how to set the paths to folder locations.

```XML
<FolderLocations>
   <ProfilesDirectory>%SYSTEMDRIVE%\Profiles</ProfilesDirectory>
</FolderLocations>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
