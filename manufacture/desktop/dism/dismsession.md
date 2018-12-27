---
title: DismSession
description: DismSession
ms.assetid: a2cc94b5-0b1d-4d33-84ca-3b3db2bf2048

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismSession
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismSession


Represents an internal DISM API concept through which all servicing operations are performed.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
typedef UINT DismSession;
```

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


You can associate an offline or online Windows image with a `DISMSession` by calling the [**DismOpenSession**](dismopensession-function.md) function. All operations on images, including mounting, servicing, committing, and unmounting are done via a `DismSession`. All APIs that operate on an image accept a `DismSession` as their first parameter. You can call [**DismCloseSession**](dismclosesession-function.md) Function to release a `DISMSession`.

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platform</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported image platform</p></td>
<td><p>Windows® 7, Windows Server 2008 R2, Windows 8, Windows Server® 2012</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DISM API Functions](dism-api-functions.md)

[DISM API Constants](dism-api-constants.md)

[Using the DISM API](using-the-dism-api.md)

 

 




