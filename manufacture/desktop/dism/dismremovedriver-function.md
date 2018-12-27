---
title: DismRemoveDriver function
description: Removes an out-of-box driver from an offline image.
ms.assetid: 0555a39c-211d-407a-b8dd-135e7f7bf627
keywords: DismRemoveDriver function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRemoveDriver
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRemoveDriver function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Removes an out-of-box driver from an offline image.

Syntax
---

```
HRESULT WINAPI DismRemoveDriver(
  _In_ DismSession Session,
  _In_ PCWSTR      DriverPath
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*DriverPath* \[in\]  
The published file name of the driver that has been added to the image, for example OEM1.inf. You can use [**DismGetDrivers**](dismgetdrivers-function.md) to get the published name of the driver.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


This function only supports offline images.

**Important**  Removing a boot-critical driver can make the offline Windows image unable to boot.

 

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismRemoveDriver(Session, "Oem1.inf");
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

 

 




