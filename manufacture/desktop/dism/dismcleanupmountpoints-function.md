---
title: DismCleanupMountPoints function
description: Removes files and releases resources associated with corrupted or invalid mount paths.
ms.assetid: 6906eaf2-4ccc-4e85-b49d-5200b2e6f729
keywords: DismCleanupMountPoints function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCleanupMountPoints
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCleanupMountPoints function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Removes files and releases resources associated with corrupted or invalid mount paths.

Syntax
---

```
HRESULT WINAPI DismCleanupMountPoints(void);
```

Parameters
-------

This function has no parameters.

Return value
---------

Returns `S_OK` on success.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismCleanupMountpoints();
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


[**DismUnmountImage**](dismunmountimage-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




