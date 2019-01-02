---
title: DismRemovePackage function
description: Removes a package from an image.
ms.assetid: 23cfe5ee-0f47-4ebf-b956-d584420a98c6
keywords: DismRemovePackage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRemovePackage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRemovePackage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Removes a package from an image.

Syntax
---

```
HRESULT WINAPI DismRemovePackage(
  _In_     DismSession            Session,
  _In_     PCWSTR                 Identifier,
  _In_     DismPackageIdentifier  PackageIdentifier,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*Identifier* \[in\]  
Either an absolute path to a .cab file or the package name, depending on the *PackageIdentifier* parameter value.

*PackageIdentifier* \[in\]  
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

 

*CancelEvent* \[in, optional\]  
Optional. You can set a *CancelEvent* for this function in order to cancel the operation in progress when signaled by the client. If the *CancelEvent* is received at a stage when the operation cannot be canceled, the operation will continue and return a success code. If the *CancelEvent* is received and the operation is canceled, the image state is unknown. You should verify the image state before continuing or discard the changes and start again.

*Progress* \[in, optional\]  
Optional. A pointer to a client-defined [DismProgressCallback](dismprogresscallback.md).

*UserData* \[in, optional\]  
Optional. User defined custom data.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The **DismRemovePackage** function does not support .msu files.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismRemovePackage(Session, "C:\\packages\\test.CAB", PackagePath, NULL, NULL, NULL);
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


[**DismAddPackage**](dismaddpackage-function.md)

[**DismGetPackages**](dismgetpackages-function.md)

[**DismRemoveDriver**](dismremovedriver-function.md)

[**DismDisableFeature**](dismdisablefeature-function.md)

 

 




