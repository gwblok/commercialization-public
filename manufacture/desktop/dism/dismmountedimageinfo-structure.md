---
title: DismMountedImageInfo structure
description: Describes the metadata of a mounted image.
ms.assetid: ad36728d-e34b-4dcb-91d6-eceea591fc37
keywords: DismMountedImageInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismMountedImageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismMountedImageInfo structure


Describes the metadata of a mounted image.

Syntax
---

```
typedef struct _DismMountedImageInfo {
  PCWSTR          MountPath;
  PCWSTR          ImageFilePath;
  UINT            ImageIndex;
  DismMountMode   MountMode;
  DismMountStatus MountStatus;
} DismMountedImageInfo;
```

Members
----

**MountPath**  
A relative or absolute path to the mounted image.

**ImageFilePath**  
A relative or absolute path to the image file.

**ImageIndex**  
The index number of the image. Index numbering starts at 1.

**MountMode**  
A [DismMountMode](dismmountmode-enumeration.md) enumeration value representing whether the image is **DismReadWrite** or **DismReadOnly**.

**MountStatus**  
A [DismMountStatus](dismmountstatus-enumeration.md) enumeration value such as **DismMountStatusOk**.

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platforms:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported image platforms:</p></td>
<td><p>Windows 7, Windows Server 2008 R2, Windows PE 3.0, Windows 8, Windows Server 2012, Windows Preinstallation Environment (Windows PE) 4.0, Windows 8.1, Windows Server 2012 R2, Windows 10, Windows Server 2016</p></td>
</tr>
</tbody>
</table>

 

Requirements
---------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum supported client</p></td>
<td><p>Windows 7 [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2008 R2 [desktop apps only]</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>DismAPI.h</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[DismMountMode](dismmountmode-enumeration.md)

[DismMountStatus](dismmountstatus-enumeration.md)

[**DismGetMountedImageInfo**](dismgetmountedimageinfo-function.md)

 

 




