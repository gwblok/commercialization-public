---
title: DismCheckImageHealth function
description: Checks whether the image can be serviced or is corrupted.
ms.assetid: 22039ad7-3cdb-491e-a396-b6fd8fa5f06a
keywords: DismCheckImageHealth function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCheckImageHealth
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCheckImageHealth function


Checks whether the image can be serviced or is corrupted.

Syntax
---

```
HRESULT WINAPI WINAPI DismCheckImageHealth(
  _In_     DismSession            Session,
  _In_     BOOL                   ScanImage,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData,
  _Out_    DismImageHealthState   *ImageHealth
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*ScanImage* \[in\]  
A Boolean value that specifies whether to scan the image or just check for flags from a previous scan.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Scan the image and flag it if it is corrupted.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Check if the image has been flagged as corrupted. You can use this value if the image has already been scanned.</p></td>
</tr>
</tbody>
</table>

 

*CancelEvent* \[in, optional\]  
Optional. You can set a *CancelEvent* for this function in order to cancel the operation in progress when signaled by the client. If the *CancelEvent* is received at a stage when the operation cannot be canceled, the operation will continue and return a success code. If the *CancelEvent* is received and the operation is canceled, the image state is unknown. You should verify the image state before continuing or discard the changes and start again.

*Progress* \[in, optional\]  
Optional. A pointer to a client-defined [DismProgressCallback](dismprogresscallback.md).

*UserData* \[in, optional\]  
Optional. User defined custom data.

*ImageHealth* \[out\]  
A pointer to the [DismImageHealthState](dismimagehealthstate-enumeration.md) enumeration. The enumeration value is set during this operation.

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


If *ScanImage* is set to `True`, this function will take longer to finish.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
DismImageHealthState state;
hr = DismCheckImageHealth(Session, TRUE, NULL, NULL, NULL, &amp;state);
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
<td><p>Windows 8 [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2012 [desktop apps only]</p></td>
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


[**DismRestoreImageHealth**](dismrestoreimagehealth-function.md)

[DismImageHealthState](dismimagehealthstate-enumeration.md)

[DISM API Constants](dism-api-constants.md)

 

 




