---
title: DismCustomProperty structure
description: Describes the custom properties of a package.
ms.assetid: 78a16e0f-97d4-4564-817f-052318836535
keywords: DismCustomProperty structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCustomProperty
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCustomProperty structure


Describes the custom properties of a package. Custom properties are any properties that are not found in [DismPackage](dismpackage-structure.md) or [DismFeature](dismfeature-structure.md) structures.

Syntax
---

```
typedef struct _DismCustomProperty {
  PCWSTR Name;
  PCWSTR Value;
  PCWSTR Path;
} DismCustomProperty;
```

Members
----

**Name**  
The name of the custom property.

**Value**  
The value of the custom property.

**Path**  
The path of the custom property.

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
</tbody>
</table>

 

 




