---
title: DismGetDriverInfo function
description: Gets information about an .inf file in a specified image.
ms.assetid: 2f69fe15-d9a0-4282-8898-d5af06deb397
keywords: DismGetDriverInfo function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetDriverInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetDriverInfo function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Gets information about an .inf file in a specified image.

Syntax
---

```
HRESULT WINAPI DismGetDriverInfo(
  _In_      DismSession       Session,
  _In_      PCWSTR            DriverPath,
  _Out_     DismDriver        **Driver,
  _Out_     UINT              *Count,
  _Out_opt_ DismDriverPackage **DriverPackage
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*DriverPath* \[in\]  
A relative or absolute path to the driver .inf file.

*Driver* \[out\]  
The address of a pointer to an array of [**DismDriver**](dismdriver-structure.md) structures.

*Count* \[out\]  
Returns the number of [**DismDriver**](dismdriver-structure.md) structures that were returned.

*DriverPackage* \[out, optional\]  
Optional. A pointer to the address of a [**DismDriverPackage**](dismdriverpackage-structure.md) structure.

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


This function returns information about the .inf file installed on the image. The driver associated with the .inf file may or may not be installed in the image.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
DismDriverInfo* DriverInfo;
UINT Count;
hr = DismGetDriverInfo(Session, L"usb.inf", &amp;DriverInfo, &amp;Count, &amp;DriverPackageInfo);
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


[**DismGetDrivers**](dismgetdrivers-function.md)

[**DismAddDriver**](dismadddriver-function.md)

[**DismRemoveDriver**](dismremovedriver-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




