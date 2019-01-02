---
title: DismDriver structure
description: Describes the architecture and hardware that the driver supports.
ms.assetid: 86ddd0b9-d84a-4cc8-8137-d00a14a2e254
keywords: DismDriver structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismDriver
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismDriver structure


Describes the architecture and hardware that the driver supports. The [**DismGetDriverInfo**](dismgetdriverinfo-function.md) Function returns an object that includes an array of DismDriver structures. If you specify a *DriverPath* using the published name of the driver installed in the image, for example OEM1.inf, the array includes only the applicable hardware and architectures that are installed in the image. You can also specify a *DriverPath* using the source location of an .inf file on the technician computer. If you use the source location, the array includes all of the supported architectures and hardware that exist in the .inf file before it is installed to an architecture-specific image.

Syntax
---

```
typedef struct _DismDriver {
  PCWSTR ManufacturerName;
  PCWSTR HardwareDescription;
  PCWSTR HardwareId;
  UINT   Architecture;
  PCWSTR ServiceName;
  PCWSTR CompatibleIds;
  PCWSTR ExcludeIds;
} DismDriver;
```

Members
----

**ManufacturerName**  
The manufacturer name of the driver.

**HardwareDescription**  
A hardware description of the driver.

**HardwareId**  
The hardware ID of the driver.

**Architecture**  
The architecture of the driver.

**ServiceName**  
The service name of the driver.

**CompatibleIds**  
The compatible IDs of the driver.

**ExcludeIds**  
The exclude IDs of the driver.

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
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismGetDriverInfo**](dismgetdriverinfo-function.md)

 

 




