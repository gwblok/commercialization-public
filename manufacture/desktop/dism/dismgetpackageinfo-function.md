---
title: DismGetPackageInfo function
description: Gets standard package properties as DismGetPackages, as well as more specific package information and custom properties.
ms.assetid: d8888625-bb8c-4a44-b627-50404b040cc0
keywords: DismGetPackageInfo function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetPackageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetPackageInfo function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Gets standard package properties as [**DismGetPackages**](dismgetpackages-function.md), as well as more specific package information and custom properties.

Syntax
---

```
HRESULT WINAPI DismGetPackageInfo(
  _In_  DismSession           Session,
  _In_  PCWSTR                Identifier,
  _In_  DismPackageIdentifier PackageIdentifier,
  _Out_ DismPackageInfo       **PackageInfo
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*Identifier* \[in\]  
Either an absolute path to a .cab file or the package name, depending on the *PackageIdentifier* parameter value.

*PackageIdentifier* \[in\]  
A valid [DismPackageIdentifier](dismpackageidentifier-enumeration.md) enumeration value.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span id="PackageName"></span><span id="packagename"></span><span id="PACKAGENAME"></span>
<strong>PackageName</strong></td>
<td><p>Use this value when you want to specify a package by using the package name.</p></td>
</tr>
<tr class="even">
<td><span id="PackagePath"></span><span id="packagepath"></span><span id="PACKAGEPATH"></span>
<strong>PackagePath</strong></td>
<td><p>Use this value when you want to specify a package by using an absolute path to a .cab file or to a folder containing an expanded package.</p></td>
</tr>
<tr class="odd">
<td><span id="PackageNone"></span><span id="packagenone"></span><span id="PACKAGENONE"></span>
<strong>PackageNone</strong></td>
<td><p>Not a valid value for this function.</p></td>
</tr>
</tbody>
</table>

 

*PackageInfo* \[out\]  
A pointer to the address of an array of [DismPackageInfo](dismpackageinfo-structure.md) structures.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


You can use this function to determine whether a package is applicable to the specified image. The [DismPackageInfo](dismpackageinfo-structure.md) structure contains an **Applicable** field, which is a Boolean that returns **TRUE** if the package is applicable and **FALSE** if the package is not applicable to the specified image.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
DismPackageInfo PackageInfo;
hr = DismGetPackageInfo(Session, "C:\packages\calc.cab", PackagePath, &amp;PackageInfo);
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


[**DismGetPackages**](dismgetpackages-function.md)

[**DismRemovePackage**](dismremovepackage-function.md)

[**DismAddPackage**](dismaddpackage-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




