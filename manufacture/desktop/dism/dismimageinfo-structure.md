---
title: DismImageInfo structure
description: Describes the metadata of an image.
ms.assetid: acd4cc5c-03f5-457b-a0a6-53034d80dc75
keywords: DismImageInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismImageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismImageInfo structure


Describes the metadata of an image.

Syntax
---

```
typedef struct _DismImageInfo {
  DismImageType     ImageType;
  UINT              ImageIndex;
  PCWSTR            ImageName;
  PCWSTR            ImageDescription;
  UINT64            ImageSize;
  UINT              Architecture;
  PCWSTR            ProductName;
  PCWSTR            EditionId;
  PCWSTR            InstallationType;
  PCWSTR            Hal;
  PCWSTR            ProductType;
  PCWSTR            ProductSuite;
  UINT              MajorVersion;
  UINT              MinorVersion;
  UINT              Build;
  UINT              SpBuild;
  UINT              SpLevel;
  DismImageBootable Bootable;
  PCWSTR            SystemRoot;
  DismLanguage      *Language;
  UINT              LanguageCount;
  UINT              DefaultLanguageIndex;
  VOID              *CustomizedInfo;
} DismImageInfo;
```

Members
----

**ImageType**  
A [DismImageType](dismimagetype-enumeration.md) enumeration value such as **DismImageTypeWim**.

**ImageIndex**  
The index number, starting at 1, of the image.

**ImageName**  
The name of the image.

**ImageDescription**  
A description of the image.

**ImageSize**  
The size of the image in bytes.

**Architecture**  
The architecture of the image.

**ProductName**  
The name of the product, for example, "Microsoft Windows Operating System".

**EditionId**  
The edition of the product, for example, "Ultimate".

**InstallationType**  
A string identifying whether the installation is a `Client` or `Server` type.

**Hal**  
The hardware abstraction layer (HAL) type of the operating system.

**ProductType**  
The product type, for example, "WinNT".

**ProductSuite**  
The product suite, for example, "Terminal Server".

**MajorVersion**  
The major version of the operating system.

**MinorVersion**  
The minor version of the operating system.

**Build**  
The build number, for example, "10240".

**SpBuild**  
The service pack build.

**SpLevel**  
The service pack number.

**Bootable**  
A [DismImageBootable](dismimagebootable-enumeration.md) enumeration value such as **DismImageBootableYes**.

**SystemRoot**  
The Windows directory.

**Language**  
An array of [DismLanguage](dismlanguage-structure.md) structures representing the languages in the image.

**LanguageCount**  
The number of elements in the *language* array.

**DefaultLanguageIndex**  
The index number of the default language.

**CustomizedInfo**  
The customized information for the image file. A [**DismWimCustomizedInfo**](dismwimcustomizedinfo-structure.md) structure for a WIM file. **NULL** for a VHD image.

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


[**DismGetImageInfo**](dismgetimageinfo-function.md)

 

 




