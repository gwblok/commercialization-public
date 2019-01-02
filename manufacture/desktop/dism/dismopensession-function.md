---
title: DismOpenSession function
description: Associates an offline or online Windows image with a DISMSession.
ms.assetid: d078d3f1-96a2-4837-af50-5a9c996e792f
keywords: DismOpenSession function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismOpenSession
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismOpenSession function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Associates an offline or online Windows image with a [DISMSession](dismsession.md).

Syntax
---

```
HRESULT WINAPI DismOpenSession(
  _In_     PCWSTR      ImagePath,
  _In_opt_ PCWSTR      WindowsDirectory,
  _In_opt_ PCWSTR      SystemDrive,
  _Out_    DismSession *Session
);
```

Parameters
-------

*ImagePath* \[in\]  
Set *ImagePath* to one of the following values:

-   An absolute or relative path to the root directory of an offline Windows image.
-   An absolute or relative path to the root directory of a mounted Windows image. You can mount the image before calling **DismOpenSession** by using an external tool or by using [**DismMountImage**](dismmountimage-function.md).
-   **DISM\_ONLINE\_IMAGE** to associate the *Session* with the online Windows installation.

*WindowsDirectory* \[in, optional\]  
Optional. A relative or absolute path to the Windows directory. The path is relative to the mount point.

If the value of *WindowsDirectory* is **NULL**, the default value of "Windows" is used.

The *WindowsDirectory* parameter cannot be used when the *ImagePath* parameter is set to **DISM\_ONLINE\_IMAGE**.

*SystemDrive* \[in, optional\]  
Optional. The letter of the system drive that contains the boot manager. If *SystemDrive* is **NULL**, the default value of the drive containing the mount point is used.

The *SystemDrive* parameter cannot be used when the *ImagePath* parameter is set to **DISM\_ONLINE\_IMAGE**.

*Session* \[out\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the **DismOpenSession**.

Return value
---------

Returns **S\_OK** on success.

Returns `HRESULT_FROM_WIN32(ERROR_ALREADY_EXISTS)` if the [DismSession](dismsession.md) already has an image associated with it.

Returns a Win32 error code mapped to an **HRESULT** for other errors.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The [DismSession](dismsession.md) can be used to service the image after the **DismOpenSession** call is successfully completed. The DismSession must be shut down by calling [**DismCloseSession**](dismclosesession-function.md).

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
DismSession Session = DISM_SESSION_DEFAULT;
hr = DismOpenSession(L"C:\\Mount\\", NULL, NULL, &amp;Session);
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


[DismSession](dismsession.md)

[**DismCloseSession**](dismclosesession-function.md)

[**DismMountImage**](dismmountimage-function.md)

 

 




