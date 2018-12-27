---
title: DismGetPackages function
description: Lists each package in an image, providing basic information including the package name and type of package.
ms.assetid: d04bafe0-7fdf-47c2-978e-fa0041525bac
keywords: DismGetPackages function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetPackages
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetPackages function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Lists each package in an image, providing basic information including the package name and type of package.

Syntax
---

```
HRESULT WINAPI DismGetPackages(
  _In_  DismSession Session,
  _Out_ DismPackage **Package,
  _Out_ UINT        *Count
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image.

*Package* \[out\]  
A pointer to the array of [DismPackage](dismpackage-structure.md) structures.

*Count* \[out\]  
The number of [DismPackage](dismpackage-structure.md) structures that are returned.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


&gt;When you are finished with the *Package* array, you must remove it by using [**DismDelete**](dismdelete-function.md).

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT      hr      = S_OK;
DismPackage* Package = NULL;
UINT         Count   = 0;
hr = DismGetPackages(Session, &amp;Package, &amp;Count);
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


[**DismDelete**](dismdelete-function.md)

[**DismGetPackageInfo**](dismgetpackageinfo-function.md)

[**DismRemovePackage**](dismremovepackage-function.md)

[**DismAddPackage**](dismaddpackage-function.md)

 

 




