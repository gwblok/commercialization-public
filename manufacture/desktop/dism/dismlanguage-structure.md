---
title: DismLanguage Structure
description: DismLanguage Structure
ms.assetid: cf3c8b20-e3db-40c2-91f5-6c7c341bc44e

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismLanguage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismLanguage Structure


Describes the language of the image.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
typedef DismString DismLanguage
```

``` syntax
typedef struct _DismString
{
    PCWSTR Value;
}
DismString;
```

## <span id="Members"></span><span id="members"></span><span id="MEMBERS"></span>Members


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Member Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>A null-terminated Unicode string.</p></td>
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
<td><p>Windows® 7, Windows Server 2008 R2, Windows PE 3.0, Windows 8, Windows Server® 2012, Windows Preinstallation Environment (Windows PE) 4.0</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DismImageInfo Structure](dismimageinfo-structure.md)

 

 




