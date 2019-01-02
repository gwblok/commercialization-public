---
title: DismCommitImage function
description: Commits the changes made to a Windows® image in a mounted .wim or .vhd file.
ms.assetid: bd4d3df9-7109-4ce5-a998-8afd0b5962a1
keywords: DismCommitImage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCommitImage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCommitImage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Commits the changes made to a Windows® image in a mounted .wim or .vhd file. The image must be mounted using the [**DismMountImage**](dismmountimage-function.md).

Syntax
---

```
HRESULT WINAPI DismCommitImage(
  _In_     DismSession            Session,
  _In_     DWORD                  Flags,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*Flags* \[in\]  
The commit flags to use for this operation. For more information about mount flags, see [DISM API Constants](dism-api-constants.md).

*CancelEvent* \[in, optional\]  
The commit flags to use for this operation. For more information about mount flags, see [DISM API Constants](dism-api-constants.md).

*Progress* \[in, optional\]  
Optional. A pointer to a client-defined [DismProgressCallback](dismprogresscallback.md).

*UserData* \[in, optional\]  
Optional. User defined custom data.

Return value
---------

Returns `S_OK` on success.

Returns `E_INVALIDARG` if the [DismSession](dismsession.md) is invalid or if the DismSession is not associated with a mounted image.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The **DismCommitImage** function does not unmount the image.

**Note**  
**DismCommitImage** can only be used on an image that is mounted within the DISM infrastructure. It does not apply to images mounted by another tool, such as the DiskPart tool, which are serviced using the [**DismOpenSession**](dismopensession-function.md). You must use the [**DismMountImage**](dismmountimage-function.md) to mount an image within the DISM infrastructure.

 

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismCommitImage(Session, 0, NULL, NULL, NULL);
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


[**DismMountImage**](dismmountimage-function.md)

[**DismUnmountImage**](dismunmountimage-function.md)

[DISM API Constants](dism-api-constants.md)

 

 




