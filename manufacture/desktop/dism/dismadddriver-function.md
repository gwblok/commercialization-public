---
title: DismAddDriver function
description: Adds a third party driver (.inf) to an offline Windows® image.
ms.assetid: 0FE3AA80-258A-4661-8AEB-F5302F683748
keywords: DismAddDriver function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismAddDriver
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismAddDriver function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Adds a third party driver (.inf) to an offline Windows® image.

Syntax
---

```
HRESULT WINAPI DismAddDriver(
  _In_ DismSession Session,
  _In_ PCWSTR      DriverPath,
  _In_ BOOL        ForceUnsigned
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md) function.

*DriverPath* \[in\]  
A relative or absolute path to the driver .inf file.

*ForceUnsigned* \[in\]  
A Boolean value that specifies whether to accept unsigned drivers to an x64-based image. Unsigned drivers will automatically be added to an x86-based image.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Add unsigned drivers to an x64-based image.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Do not add unsigned drivers to an x64-based image.</p></td>
</tr>
</tbody>
</table>

 

Return value
---------

Returns `S_OK` on success.

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

 

Examples
-----

In this example, the driver being added is located on the technician computer in the folder C:\\drivers\\. The driver has the filename usb.inf on the technician computer, but is renamed to "OEM1.inf" or "OEM2.inf" in the target image. The numbering of the OEMx.inf files is dependent on the number of drivers added. The new name, for example OEM1.inf, is returned in the [DismDriverPackage](dismdriverpackage-structure.md) structure when you call the [**DismGetDrivers**](dismgetdrivers-function.md). You should use the new name, OEM1.inf, to specify the *DriverPath* when you use the [**DismGetDriverInfo**](dismgetdriverinfo-function.md).

``` syntax
HRESULT hr = S_OK;
hr = DismAddDriver(Session, L"C:\\Drivers\\usb.inf", FALSE);
```

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

 

 




