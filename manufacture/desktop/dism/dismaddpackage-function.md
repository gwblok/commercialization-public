---
title: DismAddPackage function
description: Adds a single .cab or .msu file to a Windows® image.
ms.assetid: 51897c3b-2916-4e5c-a7bc-be591ec9bf73
keywords: DismAddPackage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismAddPackage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismAddPackage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Adds a single .cab or .msu file to a Windows® image.

Syntax
---

```
HRESULT WINAPI DismAddPackage(
  _In_     DismSession            Session,
  _In_     PCWSTR                 PackagePath,
  _In_     BOOL                   IgnoreCheck,
  _In_     BOOL                   PreventPending,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*PackagePath* \[in\]  
A relative or absolute path to the .cab or .msu file being added, or a folder containing the expanded files of a single .cab file.

*IgnoreCheck* \[in\]  
A Boolean value to specify whether to ignore the internal applicability checks that are done when a package is added.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Ignore the internal applicability checks.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Do not ignore the internal applicability checks.</p></td>
</tr>
</tbody>
</table>

 

*PreventPending* \[in\]  
A Boolean value to specify whether to add a package if it has pending online actions.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Prevent the installation of a package that has pending online actions.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Allow the installation of a package that has pending online actions.</p></td>
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

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


Only .cab files can be added to an online image. Either .cab or .msu files can be added to an offline image.

This function will return a special error code if the package is not applicable. You can use the [**DismGetPackageInfo**](dismgetpackageinfo-function.md) to determine if a package is applicable to the target image.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismAddPackage(Session, "C:\\packages\\calc.cab", FALSE, FALSE, NULL, NULL, NULL);
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

[**DismEnableFeature**](dismenablefeature-function.md)

[**DismGetPackages**](dismgetpackages-function.md)

[**DismGetPackageInfo**](dismgetpackageinfo-function.md)

[**DismRemovePackage**](dismremovepackage-function.md)

[DismPackage](dismpackagefeaturestate-enumeration.md)

[DismPackageInfo](dismpackageinfo-structure.md)

DismPackageFeatureState
 

 




