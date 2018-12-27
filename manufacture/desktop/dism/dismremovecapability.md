---
title: DismRemoveCapability function
description: Add a capability to an image.
ms.assetid: 0DF0B46F-7FCE-490D-A7CC-C81F2F16E86B
keywords: DismRemoveCapability function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRemoveCapability
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRemoveCapability function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Add a capability to an image.

Syntax
---

```
HRESULT WINAPI DismRemoveCapability(
  _In_     DismSession             Session,
  _In_     PCWSTR                  Name,
  _In_opt_ HANDLE                  CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK  Progress,
  _In_opt_ PVOID                   UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*Name* \[in\]  
The name of the capability that is being removed

*CancelEvent* \[in, optional\]  
This is a handle to an event for cancellation.

*Progress* \[in, optional\]  
Pointer to a client defined callback function to report progress.

*UserData* \[in, optional\]  
User defined custom data. This will be passed back to the user through the callback.

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


Use this function to remove a capability.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismRemoveCapability(Session, L“Language.Basic~~~en-US~0.0.1.0”, NULL, NULL, NULL);
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
<td><p>Windows 10, Windows Server 2016</p></td>
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
<td><p>Windows 10 [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2016 [desktop apps only]</p></td>
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
 

 




