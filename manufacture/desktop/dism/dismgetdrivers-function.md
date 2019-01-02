---
title: DismGetDrivers function
description: Lists the drivers in an image.
ms.assetid: 49731558-d7ef-4fdc-839a-f6483f6e51ba
keywords: DismGetDrivers function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetDrivers
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetDrivers function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Lists the drivers in an image.

Syntax
---

```
HRESULT WINAPI DismGetDrivers(
  _In_  DismSession       Session,
  _In_  BOOL              AllDrivers,
  _Out_ DismDriverPackage **DriverPackage,
  _Out_ UINT              *Count
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*AllDrivers* \[in\]  
A Boolean value specifying which drivers to retrieve.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Retrieve all drivers.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Retrieve only out-of-box drivers. <em>Out-of-box drivers</em> are drivers that were not originally included in the Windows image.</p></td>
</tr>
</tbody>
</table>

 

*DriverPackage* \[out\]  
A pointer to the address of an array of [**DismDriverPackage**](dismdriverpackage-structure.md) structures.

*Count* \[out\]  
The number of [**DismDriverPackage**](dismdriverpackage-structure.md) structures that were returned.

Return value
---------

Returns `S_OK` on success.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
DismDriver* DriverPackageInfos;
UINT Count;
hr = DismGetDrivers(Session, TRUE, &amp;DriverPackageInfos, &amp;Count);
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


[**DismAddDriver**](dismadddriver-function.md)

[**DismRemoveDriver**](dismremovedriver-function.md)

[**DismGetDriverInfo**](dismgetdriverinfo-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




