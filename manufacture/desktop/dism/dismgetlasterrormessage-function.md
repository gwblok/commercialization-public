---
title: DismGetLastErrorMessage function
description: Gets the error message in the current thread, immediately after a failure.
ms.assetid: bd07d96b-e2b5-4d3a-8473-760087e5a3b1
keywords: DismGetLastErrorMessage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetLastErrorMessage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetLastErrorMessage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Gets the error message in the current thread, immediately after a failure.

Syntax
---

```
HRESULT WINAPI DismGetLastErrorMessage(
  _Out_ DismString **ErrorMessage
);
```

Parameters
-------

*ErrorMessage* \[out\]  
The detailed error message in the current thread.

Return value
---------

Returns **S\_OK** on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


You can get a detailed error message immediately after a DISM API failure. The last error message is maintained on a per-thread basis. An error message on a thread will not overwrite the last error message on another thread.

**DismGetLastErrorMessage** does not apply to the [**DismShutdown**](dismshutdown-function.md) function, [**DismDelete**](dismdelete-function.md) function, or the **DismGetLastErrorMessage** function.

You must call the [**DismDelete**](dismdelete-function.md) function to free the memory of *ErrorMessage* when the return value is **S\_OK**.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


``` syntax
HRESULT hr = S_OK;
DismString* ErrorMessage;
hr = DismGetLastErrorMessage(&ErrorMessage);
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


[DISM API Troubleshooting](dism-api-troubleshooting.md)

 

 




