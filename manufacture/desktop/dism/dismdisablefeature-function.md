---
title: DismDisableFeature function
description: Disables a feature in the current image.
ms.assetid: d6f6d7ae-a205-4981-b40c-390f16cbe088
keywords: DismDisableFeature function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismDisableFeature
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismDisableFeature function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Disables a feature in the current image.

Syntax
---

```
HRESULT WINAPI DismDisableFeature(
  _In_     DismSession            Session,
  _In_     PCWSTR                 FeatureName,
  _In_opt_ PCWSTR                 PackageName,
  _In_     BOOL                   RemovePayload,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*FeatureName* \[in\]  
The name of the feature that you want to disable. To disable more than one feature, separate each feature name with a semicolon.

*PackageName* \[in, optional\]  
Optional. The name of the parent package that the feature is a part of. If no package is specified, then the default Windows® Foundation package is used.

*RemovePayload* \[in\]  
This parameter is not supported starting withWindows 8.1 and Windows Server 2012 R2.

**Windows 8 and Windows Server 2012:  **

A Boolean value specifying whether to remove the files required to enable the feature.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>The files are removed.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>The files are not removed.</p></td>
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

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismDisableFeature(Session, "WindowsMediaPlayer", NULL, FALSE, NULL, NULL, NULL);
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

[**DismGetFeatures**](dismgetfeatures-function.md)

[**DismGetFeatureInfo**](dismgetfeatureinfo-function.md)

 

 




