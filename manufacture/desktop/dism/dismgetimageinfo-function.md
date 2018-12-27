---
title: DismGetImageInfo function
description: Returns an array of DismImageInfo structures that describe the images in a .wim or .vhd file.
ms.assetid: 1b8570a4-1bdd-4c36-bd95-8b693ca61737
keywords: DismGetImageInfo function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetImageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetImageInfo function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Returns an array of [DismImageInfo](dismimageinfo-structure.md) structures that describe the images in a .wim or .vhd file.

Syntax
---

```
HRESULT WINAPI DismGetImageInfo(
  _In_  PCWSTR        ImageFilePath,
  _Out_ DismImageInfo **ImageInfo,
  _Out_ UINT          *Count
);
```

Parameters
-------

*ImageFilePath* \[in\]  
A relative or absolute path to a .wim or .vhd file.

*ImageInfo* \[out\]  
A pointer to the address of an array of [DismImageInfo](dismimageinfo-structure.md) structures.

*Count* \[out\]  
The number of [DismImageInfo](dismimageinfo-structure.md) structures that are returned.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The array of [DismImageInfo](dismimageinfo-structure.md) structures are allocated by DISM API on the heap.

**Important**  You must call [**DismDelete**](dismdelete-function.md), passing the *ImageInfo* pointer, to free the resources associated with the [DismImageInfo](dismimageinfo-structure.md) structures.

 

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
UINT* ImageInfoCount; 
hr = DismGetImageInfo(L"C:\\Images\\Image1.vhd", &amp;ImageInfo, &amp;ImageInfoCount);
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

 

## <span id="see_also"></span>See also


[DismImageInfo](dismimageinfo-structure.md)

[**DismGetMountedImageInfo**](dismgetmountedimageinfo-function.md)

[DismMountedImageInfo](dismmountedimageinfo-structure.md)

[**DismDelete**](dismdelete-function.md)

 

 




