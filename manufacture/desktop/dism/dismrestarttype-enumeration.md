---
title: DismRestartType Enumeration
description: DismRestartType Enumeration
ms.assetid: 8ca81605-d8cf-4c92-a09a-f5d0114afb4b

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRestartType
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRestartType Enumeration


Specifies whether a restart is required after enabling a feature or installing a package.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismRestartType
{
    DismRestartNo = 0,
    DismRestartPossible = 1,
    DismRestartRequired = 2
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
<td><p><em>DismRestartNo</em></p></td>
<td><p>0</p></td>
<td><p>No restart is required.</p></td>
</tr>
<tr class="even">
<td><p><em>DismRestartPossible</em></p></td>
<td><p>1</p></td>
<td><p>This package or feature might require a restart.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismRestartRequired</em></p></td>
<td><p>2</p></td>
<td><p>This package or feature always requires a restart.</p></td>
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


[DismPackageInfo Structure](dismpackageinfo-structure.md)

[DismFeatureInfo Structure](dismfeatureinfo-structure.md)

 

 




