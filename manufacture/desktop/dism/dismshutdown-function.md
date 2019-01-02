---
title: DismShutdown function
description: Shuts down DISM API. DismShutdown must be called once per process.
ms.assetid: 2a1593ed-ceb3-4944-a56d-9172e8c3ff72
keywords: DismShutdown function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismShutdown
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismShutdown function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Shuts down DISM API. **DismShutdown** must be called once per process. Other DISM API function calls will fail after **DismShutdown** has been called.

Syntax
---

```
HRESULT WINAPI DismShutdown(void);
```

Parameters
-------

This function has no parameters.

Return value
---------

Returns **S\_OK** on success.

Returns **DISMAPI\_E\_DISMAPI\_NOT\_INITIALIZED** if [**DismInitialize**](disminitialize-function.md) has not been called.

Returns **DISMAPI\_E\_OPEN\_SESSION\_HANDLES** if any open [DismSession](dismsession.md) have not been closed.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


You must call **DismShutdown** once per process. Calls to **DismShutdown** must be matched to an earlier call to [**DismInitialize**](disminitialize-function.md). DISM API will serialize concurrent calls to **DismShutdown**. The first call will succeed and the other calls will fail.

Before calling **DismShutdown**, you must close all [DismSession](dismsession.md) using [**DismCloseSession**](dismclosesession-function.md). If there are open DismSessions when calling **DismShutdown**, then the **DismShutdown** call will fail. For more information, see [Using the DISM API](using-the-dism-api.md).

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
hr = DismShutdown();
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


[**DismInitialize**](disminitialize-function.md)

[DismSession](dismsession.md)

[**DismCloseSession**](dismclosesession-function.md)

 

 




