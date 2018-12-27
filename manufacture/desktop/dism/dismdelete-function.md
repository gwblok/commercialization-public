---
title: DismDelete function
description: Releases resources held by a structure or an array of structures returned by other DISM API Functions.
ms.assetid: df65e1b2-65b2-4825-bc09-b46c99da742d
keywords: DismDelete function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismDelete
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismDelete function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Releases resources held by a structure or an array of structures returned by other [DISM API Functions](dism-api-functions.md).

Syntax
---

```
HRESULT WINAPI DismDelete(
  _In_ VOID *DismStructure
);
```

Parameters
-------

*DismStructure* \[in\]  
A pointer to the structure, or array of structures, to be deleted. The structure must have been returned by an earlier call to a [DISM API function](dism-api-functions.md).

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


All structures that are returned by DISM API functions are allocated on the heap. The client must not delete or free these structures directly. Instead, the client should call **DismDelete** and pass in the pointer that was returned by the earlier DISM API call.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


``` syntax
HRESULT hr = S_OK; 
hr = DismDelete(ImageInfo);
```

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


[DISM API Functions](dism-api-functions.md)

[**DismAddDriver**](dismadddriver-function.md)

 

 




