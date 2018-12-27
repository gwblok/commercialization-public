---
title: DismDriverPackage structure
description: Contains basic information for the driver that is associated with the .inf file.
ms.assetid: ea048bd3-e0a2-4ffc-8ac0-cf61cb4c8f17
keywords: DismDriverPackage structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismDriverPackage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismDriverPackage structure


Contains basic information for the driver that is associated with the .inf file.

Syntax
---

```
typedef struct _DismDriverPackage {
  PCWSTR              PublishedName;
  PCWSTR              OriginalFileName;
  BOOL                InBox;
  PCWSTR              CatalogFile;
  PCWSTR              ClassName;
  PCWSTR              ClassGuid;
  PCWSTR              ClassDescription;
  BOOL                BootCritical;
  DismDriverSignature DriverSignature;
  PCWSTR              ProviderName;
  SYSTEMTIME          Date;
  UINT                MajorVersion;
  UINT                MinorVersion;
  UINT                Build;
  UINT                Revision;
} DismDriverPackage;
```

Members
----

**PublishedName**  
The published driver name.

**OriginalFileName**  
The original file name of the driver.

**InBox**  
`TRUE` if the driver is included on the Windows distribution media and automatically installed as part of Windows®, otherwise `FALSE`.

**CatalogFile**  
The catalog file for the driver.

**ClassName**  
The class name of the driver.

**ClassGuid**  
The class **GUID** of the driver.

**ClassDescription**  
The class description of the driver.

**BootCritical**  
`TRUE` if the driver is boot-critical, otherwise `FALSE`.

**DriverSignature**  
A value from the [DismDriverSignature](dismdriversignature-enumeration.md) enumeration that indicates the driver signature status.

**ProviderName**  
The provider of the driver.

**Date**  
The manufacturer's build date of the driver.

**MajorVersion**  
The major version number of the driver.

**MinorVersion**  
The minor version number of the driver.

**Build**  
The build number of the driver.

**Revision**  
The revision number of the driver.

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


[**DismGetDrivers**](dismgetdrivers-function.md)

 

 




