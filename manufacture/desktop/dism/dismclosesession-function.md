---
title: DismCloseSession function
description: Closes a DISMSession created by DismOpenSession. This function does not unmount the image. To unmount the image, use the DismUnmountImage once all sessions are closed.
ms.assetid: c52b57e3-e2d3-47f0-80a9-65d568e01ae3
keywords: DismCloseSession function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCloseSession
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCloseSession function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Closes a [DISMSession](dismsession.md) created by [**DismOpenSession**](dismopensession-function.md). This function does not unmount the image. To unmount the image, use the [**DismUnmountImage**](dismunmountimage-function.md) once all sessions are closed.

Syntax
---

```
HRESULT WINAPI DismCloseSession(
  _In_ DismSession Session
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

Return value
---------

Returns `S_OK` on success.

If the [DISMSession](dismsession.md) is performing operations on other threads, those operations will complete before the DISMSession is destroyed. If additional operations are invoked by other threads after **DismCloseSession** is called, but before **DismCloseSession** returns, those operations will fail and return a `DISMAPI_E_INVALID_DISM_SESSION` error.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The [DISMSession](dismsession.md) will be shut down after this call is completed but the image will not be unmounted. To unmount the image, use the [**DismUnmountImage**](dismunmountimage-function.md) once all sessions are closed.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
DismSession session; 
hr = DismOpenSession( DISM_ONLINE_IMAGE, NULL, NULL, &amp;session ); 
hr = DismCloseSession( session );
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


[**DismOpenSession**](dismopensession-function.md)

[DISMSession](dismsession.md)

 

 




