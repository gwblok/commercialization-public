---
title: DismInitialize function
description: Initializes DISM API. DismInitialize must be called once per process, before calling any other DISM API functions.
ms.assetid: e387b740-8c89-4de4-b736-b06a3b99fa57
keywords: DismInitialize function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismInitialize
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismInitialize function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Initializes DISM API. **DismInitialize** must be called once per process, before calling any other DISM API functions.

Syntax
---

```
HRESULT WINAPI DismInitialize(
  _In_     DismLogLevel LogLevel,
  _In_opt_ PCWSTR       LogFilePath,
  _In_opt_ PCWSTR       ScratchDirectory
);
```

Parameters
-------

*LogLevel* \[in\]  
A [DismLogLevel](dismloglevel-enumeration.md) enumeration value, such as **DismLogErrorsWarnings**.

*LogFilePath* \[in, optional\]  
Optional. A relative or absolute path to a log file. All messages generated will be logged to this path. If **NULL**, the default log path, %windir%\\Logs\\DISM\\dism.log, will be used.

*ScratchDirectory* \[in, optional\]  
Optional. A relative or absolute path to a scratch directory. DISM API will use this directory for internal operations. If **NULL**, the default temp directory, \\Windows\\%Temp%, will be used.

Return value
---------

Returns **S\_OK** on success.

Returns **DISMAPI\_E\_DISMAPI\_ALREADY\_INITIALIZED** if **DismInitialize** has already been called by the process without a matching call to [**DismShutdown**](dismshutdown-function.md).

Returns `HRESULT_FROM_WIN32(ERROR_ELEVATION_REQUIRED)` if the process is not elevated.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


The client code must call **DismInitialize** once per process. DISM API will serialize concurrent calls to **DismInitialize**. The first call will succeed and the others will fail. For more information, see [Using the DISM API](using-the-dism-api.md).

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


``` syntax
HRESULT hr = S_OK;
DismLogLevel Level = DismLogErrorsWarningsInfo;
hr = DismInitialize(Level, NULL, NULL);
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


[DismLogLevel](dismloglevel-enumeration.md)

[**DismShutdown**](dismshutdown-function.md)

 

 




