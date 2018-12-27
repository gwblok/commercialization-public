---
title: DismMountImage function
description: Mounts a WIM or VHD image file to a specified location.
ms.assetid: 0ae41269-8735-41ff-9dcd-f0274f0d194e
keywords: DismMountImage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismMountImage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismMountImage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Mounts a WIM or VHD image file to a specified location.

Syntax
---

```
HRESULT WINAPI DismMountImage(
  _In_     PCWSTR                 ImageFilePath,
  _In_     PCWSTR                 MountPath,
  _In_     UINT                   ImageIndex,
  _In_opt_ PCWSTR                 ImageName,
  _In_     DismImageIdentifier    ImageIdentifier,
  _In_     DWORD                  Flags,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*ImageFilePath* \[in\]  
The path to the WIM or VHD file on the local computer. A .wim, .vhd, or .vhdx file name extension is required.

*MountPath* \[in\]  
The path of the location where the image should be mounted. This mount path must already exist on the computer. The Windows image in a .wim, .vhd, or .vhdx file can be mounted to an empty folder on an NTFS formatted drive. A Windows image in a .vhd or .vhdx file can also be mounted to an unassigned drive letter. You cannot mount an image to the root of the existing drive.

*ImageIndex* \[in\]  
The index of the image in the WIM file that you want to mount. For a VHD file, you must specify an index of `1`.

*ImageName* \[in, optional\]  
Optional. The name of the image that you want to mount.

*ImageIdentifier* \[in\]  
A [DismImageIdentifier](dismimageidentifier-enumeration.md) enumeration value such as **DismImageIndex**.

*Flags* \[in\]  
The mount flags to use for this operation. For more information about mount flags, see [DISM API Constants](dism-api-constants.md).

*CancelEvent* \[in, optional\]  
Optional. You can set a *CancelEvent* for this function in order to cancel the operation in progress when signaled by the client. If the *CancelEvent* is received at a stage when the operation cannot be canceled, the operation will continue and return a success code. If the *CancelEvent* is received and the operation is canceled, the image state is unknown. You should verify the image state before continuing or discard the changes and start again.

*Progress* \[in, optional\]  
Optional. A pointer to a client-defined [DismProgressCallback](dismprogresscallback.md) function.

*UserData* \[in, optional\]  
Optional. User defined custom data.

Return value
---------

Returns **S\_OK** on success.

Returns **E\_INVALIDARG** if any of the paths are not well-formed or if *MountPath* or *ImageFilePath* does not exist or is invalid.

Returns a Win32 error code mapped to an **HRESULT** for other errors.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


After mounting an image, use [**DismOpenSession**](dismopensession-function.md) to start a servicing session. For more information, see [Using the DISM API](using-the-dism-api.md).

Mounting an image from a WIM or VHD file that is stored on the network is not supported. You must specify a file on the local computer.

To mount an image from a VHD file, you must specify an *ImageIndex* of `1`.

The *MountPath* must be a file path that already exists on the computer. Images in WIM and VHD files can be mounted to an empty folder on an NTFS formatted drive. You can also mount an image from a VHD file to an unassigned drive letter. You cannot mount an image to the root of the existing drive.

When mounting an image in a WIM file, the image can either be identified by the image index number specified by *ImageIndex*, or the name of the image specified by *ImageName*. *ImageIdentifier* specifies whether to use the *ImageIndex* or *ImageName* parameter to identify the image.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismMountImage(L” C:\\test\\images\\myimage.wim”, L"C:\\test\\offline", 1, NULL, DismImageIndex, DISM_MOUNT_READWRITE, NULL, NULL, NULL);
```

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platforms for .wim files:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported host platforms for .vhd and .vhdx files:</p></td>
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
<tr class="even">
<td><p>Library</p></td>
<td>DismAPI.lib</td>
</tr>
<tr class="odd">
<td><p>DLL</p></td>
<td>DismAPI.dll</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismUnmountImage**](dismunmountimage-function.md)

[**DismOpenSession**](dismopensession-function.md)

 

 




