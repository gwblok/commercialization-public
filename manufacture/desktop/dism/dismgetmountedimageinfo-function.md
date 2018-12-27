---
title: DismGetMountedImageInfo function
description: Returns an array of DismMountedImageInfo structures describing currently mounted images.
ms.assetid: 6c1118ed-540d-4ce3-bc24-66b83e8a8790
keywords: DismGetMountedImageInfo function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetMountedImageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetMountedImageInfo function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Returns an array of [DismMountedImageInfo](dismmountedimageinfo-structure.md) structures describing currently mounted images.

Syntax
---

```
HRESULT WINAPI DismGetMountedImageInfo(
  _Out_ DismMountedImageInfo **MountedImageInfo,
  _Out_ UINT                 *Count
);
```

Parameters
-------

*MountedImageInfo* \[out\]  
A pointer to the address of an array of [DismMountedImageInfo](dismmountedimageinfo-structure.md) structures.

*Count* \[out\]  
The number of [DismMountedImageInfo](dismmountedimageinfo-structure.md) structures that are returned.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


**Important**  Only images mounted using the DISM infrastructure will be returned. If a .vhd file is mounted outside of DISM, such as with the DiskPart tool, this call will not return information about that image. You must use [**DismMountImage**](dismmountimage-function.md) to mount the image.

 

The array of [DismMountedImageInfo](dismmountedimageinfo-structure.md) structures are allocated by the DISM API on the heap.

**Important**  You must call [**DismDelete**](dismdelete-function.md), passing the *ImageInfo* pointer, to free the resources associated with the [DismImageInfo](dismimageinfo-structure.md) structures.

 

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


``` syntax
HRESULT hr = S_OK; 
DismMountedImageInfo* ImageInfo; 
UINT& ImageInfoCount; 
hr = DismGetMountedImageInfo(&ImageInfo, &ImageInfoCount);
```

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platform for .wim images:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported host platform for .vhd images:</p></td>
<td><p>Windows 7, Windows Server 2008 R2, Windows 8, Windows Server 2012, Windows 8.1, Windows Server 2012 R2, Windows 10, Windows Server 2016</p></td>
</tr>
<tr class="odd">
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


[DismMountedImageInfo](dismmountedimageinfo-structure.md)

[**DismGetImageInfo**](dismgetimageinfo-function.md)

[**DismMountImage**](dismmountimage-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




