---
title: DismImageType Enumeration
description: DismImageType Enumeration
ms.assetid: d41e1547-6e3b-4ff5-801f-8f810b4811fa

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismImageType
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismImageType Enumeration


Specifies the file type of the Windows® image container.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismImageType
{
    DismImageTypeUnsupported = -1,
    DismImageTypeWim = 0,
    DismImageTypeVhd = 1
};
```

## <span id="Constants"></span><span id="constants"></span><span id="CONSTANTS"></span>Constants


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>DismImageTypeUnsupported</em></p></td>
<td><p>-1</p></td>
<td><p>The file type is unsupported. The image must be in a .wim, .vhd, or .vhdx file.</p></td>
</tr>
<tr class="even">
<td><p><em>DismImageTypeWim</em></p></td>
<td><p>0</p></td>
<td><p>The image is in a .wim file.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismImageTypeVhd</em></p></td>
<td><p>1</p></td>
<td><p>The image is in a .vhd or .vhdx file.</p></td>
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
<td><p>Windows® 7, Windows Server 2008 R2, Windows Preinstallation Environment 3.0, Windows 8, Windows Server® 2012, Windows Preinstallation Environment (Windows PE) 4.0</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DismImageInfo Structure](dismimageinfo-structure.md)

 

 




