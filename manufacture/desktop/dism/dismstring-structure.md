---
title: DismString structure
description: DISM API functions that return strings wrap the heap allocated PCWSTR in a DismString structure.
ms.assetid: f3246280-d805-45d8-9f79-18adb804822a
keywords: DismString structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismString
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismString structure


DISM API functions that return strings wrap the heap allocated **PCWSTR** in a DismString structure.

Syntax
---

```
typedef struct _DismString {
  PCWSTR Value;
} DismString;
```

Members
----

**Value**  
A null-terminated Unicode string.

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
</tbody>
</table>

## <span id="see_also"></span>See also


[DismImageInfo](dismimageinfo-structure.md)

 

 




