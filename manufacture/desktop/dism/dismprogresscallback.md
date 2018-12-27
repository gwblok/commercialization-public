---
title: DismProgressCallback
description: DismProgressCallback
ms.assetid: 261a3763-86ed-4aea-b84d-bc3807c61c8c

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismProgressCallback
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismProgressCallback


A client-defined callback function that DISM API uses to report progress on time-consuming operations. API functions that report progress accept a pointer to a DismProgressCallback function. DISM\_PROGRESS\_CALLBACK is a typedef to this function type.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
void
DismProgressCallback(
    _In_ UINT Current,
    _In_ UINT Total,
    _In_ PVOID UserData
    )

typedef void (*DISM_PROGRESS_CALLBACK)(UINT, UINT, PVOID)
```

## <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Current</em></p></td>
<td><p>The current progress value.</p></td>
</tr>
<tr class="even">
<td><p><em>Total</em></p></td>
<td><p>The total progress value.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserData</em></p></td>
<td><p>User defined custom data. This parameter can be passed to another DISM function that accepts a progress callback and that function will then pass it through to DismProgressCallback.</p></td>
</tr>
</tbody>
</table>

 

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
<td><p>Windows® 7, Windows Server 2008 R2, Windows 8, Windows Server® 2012</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DISM API Functions](dism-api-functions.md)

 

 




