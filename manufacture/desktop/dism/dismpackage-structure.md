---
title: DismPackage structure
description: Describes basic information about a package, including the date and time that the package was installed.
ms.assetid: 0140fe96-f0be-4ff3-a8ea-1a2e7c62c3fe
keywords: DismPackage structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismPackage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismPackage structure


Describes basic information about a package, including the date and time that the package was installed.

Syntax
---

```
typedef struct _DismPackage {
  PCWSTR                  PackageName;
  DismPackageFeatureState PackageState;
  DismReleaseType         ReleaseType;
  SYSTEMTIME              InstallTime;
} DismPackage;
```

Members
----

**PackageName**  
The package name.

**PackageState**  
A [DismPackageFeatureState Enumeration](dismpackagefeaturestate-enumeration.md) value, for example, `DismStateResolved`.

**ReleaseType**  
A [DismReleaseType Enumeration](dismreleasetype-enumeration.md) value, for example, `DismReleaseTypeDriver`.

**InstallTime**  
The date and time that the package was installed. This field is local time relative to the servicing host computer.

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


[DismPackageFeatureState](dismpackagefeaturestate-enumeration.md)

[DismReleaseType](dismreleasetype-enumeration.md)

[**DismGetPackages**](dismgetpackages-function.md)

 

 




