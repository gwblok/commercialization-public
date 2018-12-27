---
title: DismGetFeatureInfo function
description: Gets detailed info from for the specified feature.
ms.assetid: 35514a46-e3e8-4d88-b151-527a855c8e89
keywords: DismGetFeatureInfo function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetFeatureInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetFeatureInfo function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Gets detailed info from for the specified feature.

Syntax
---

```
HRESULT WINAPI DismGetFeatureInfo(
  _In_     DismSession           Session,
  _In_     PCWSTR                FeatureName,
  _In_opt_ PCWSTR                Identifier,
  _In_opt_ DismPackageIdentifier PackageIdentifier,
  _Out_    DismFeatureInfo       **FeatureInfo
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*FeatureName* \[in\]  
The name of the feature that you want to get more information about.

*Identifier* \[in, optional\]  
Optional. Either an absolute path to a .cab file or the package name, depending on the *PackageIdentifier* parameter value.

*PackageIdentifier* \[in, optional\]  
Optional. A valid [DismPackageIdentifier](dismpackageidentifier-enumeration.md) enumeration value.

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
<td><p>Use this value when you want to specify a package by using an absolute path to a .cab file.</p></td>
</tr>
<tr class="odd">
<td><span id="PackageNone"></span><span id="packagenone"></span><span id="PACKAGENONE"></span>
<strong>PackageNone</strong></td>
<td><p>Not a valid value for this function.</p></td>
</tr>
</tbody>
</table>

 

*FeatureInfo* \[out\]  
A pointer to the address of an array of [**DismFeatureInfo**](dismfeatureinfo-structure.md) structures.

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


You can use this function to get the custom properties of a feature. If the feature has custom properties, they will be stored in the *CustomProperty* field as an array. Not all features have custom properties.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
DismFeatureInfo FeatureInfo; 
hr = DismGetFeatureInfo(Session, "Xps-Foundation-Xps-Viewer", NULL, NULL, &amp;FeatureInfo);
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


[**DismEnableFeature**](dismenablefeature-function.md)

[**DismDisableFeature**](dismdisablefeature-function.md)

[**DismGetFeatureInfo**](dismgetfeatureinfo-function.md)

[**DismGetFeatureParent**](dismgetfeatureparent-function.md)

[**DismDelete**](dismdelete-function.md)

 

 




