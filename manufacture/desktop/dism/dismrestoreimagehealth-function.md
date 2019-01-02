---
title: DismRestoreImageHealth function
description: Repairs a corrupted image that has been identified as repairable by DismCheckImageHealth.
ms.assetid: ed9c0f9a-ada1-4eea-b741-ccff7ff1afff
keywords: DismRestoreImageHealth function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRestoreImageHealth
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRestoreImageHealth function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Repairs a corrupted image that has been identified as repairable by [**DismCheckImageHealth**](dismcheckimagehealth-function.md).

Syntax
---

```
HRESULT WINAPI DismRestoreImageHealth(
  _In_     DismSession            Session,
  _In_opt_ PCWSTR                 *SourcePaths,
  _In_opt_ UINT                   SourcePathCount,
  _In_     BOOL                   LimitAccess,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*SourcePaths* \[in, optional\]  
Optional. A list of source locations to check for repair files.

*SourcePathCount* \[in, optional\]  
Optional. The number of source locations specified.

*LimitAccess* \[in\]  
A Boolean value that indicates whether the **DismRestoreImageHealth** function should contact Windows Update (WU) as a source location for downloading repair files. Before checking WU, DISM will check for the files in the *SourcePaths* provided and in any locations specified in the registry by Group Policy. If the files that are required to enable the feature are found in these other specified locations, this flag is ignored.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>TRUE</strong></p></td>
<td><p>Do not check WU for repair files.</p></td>
</tr>
<tr class="even">
<td><p><strong>FALSE</strong></p></td>
<td><p>Default. Check WU for repair files.</p></td>
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


Run [**DismCheckImageHealth**](dismcheckimagehealth-function.md) to determine if the image is corrupted and if the image is repairable. If the **DismCheckImageHealth** returns **DismImageRepairable**, the **DismRestoreImageHealth** function can repair the image.

If a repair file is not found in any of the locations specified by the *SourcePaths* parameter or the location paths in the registry specified by Group Policy, the **DismRestoreImageHealth** function will contact WU to check for a repair file unless the *LimitAccess* parameter is set to **TRUE**.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismRestoreImageHealth(Session, NULL, 0, TRUE, NULL, NULL, NULL);
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
<td><p>Windows 8, Windows Server 2012, Windows 8.1, Windows Server 2012 R2, Windows 10, Windows Server 2016</p></td>
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


[**DismCheckImageHealth**](dismcheckimagehealth-function.md)

[DismImageHealthState](dismimagehealthstate-enumeration.md)

 

 




