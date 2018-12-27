---
title: DismWimCustomizedInfo structure
description: DISM API functions for DismWimCustomizedInfo structure.
ms.assetid: 6af542b2-8dd4-4b5d-bfcd-ec31454bb818
keywords: DismWimCustomizedInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismWimCustomizedInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismWimCustomizedInfo Structure


Describes a Windows Imaging Format (WIM) file.

## Syntax

```
typedef struct _DismWimCustomizedInfo
{
    UINT Size;
    UINT DirectoryCount;
    UINT FileCount;
    SYSTEMTIME CreatedTime;
    SYSTEMTIME ModifiedTime;
}
DismWimCustomizedInfo;
```

Members

| Member Name |	Description | 
| --- | --- |
| _Size_ | The size of the **DismWimCustomizedInfo** structure. |
| _DirectoryCount_ | The number of directories in the image. |
| _FileCount_ | The number of files in the image. |
| _CreatedTime_ | The time that the image file was created. |
| _ModifiedTime_ | The time that the image file was last modified. |


## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements

| | |
| --- | --- |
| Supported host platforms: | DISM API can be used on any operating system supported by the Windows Assessment and Deployment Kit (Windows ADK). For more information, see the Windows ADK Technical Reference. |
| Supported image platforms: | Windows 7, Windows Server 2008 R2, Windows Preinstallation Environment 3.0, Windows 8, Windows Server 2012, Windows Preinstallation Environment (Windows PE) 4.0 |

 

## <span id="see_also"></span>See also


[DismImageInfo](dismimageinfo-structure.md)

 

 




