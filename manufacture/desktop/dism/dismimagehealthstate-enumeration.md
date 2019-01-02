---
title: DismImageHealthState Enumeration
description: DismImageHealthState Enumeration
ms.assetid: d1879143-8af1-4619-802c-126c9597ad6f

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismImageHealthState
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismImageHealthState Enumeration


Specifies whether an image is corrupted.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismImageHealthState
{
    DismImageHealthy = 0,
    DismImageRepairable = 1,
    DismImageNonRepairable = 2
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
<td><p><em>DismImageHealthy</em></p></td>
<td><p>0</p></td>
<td><p>The image is not corrupted.</p></td>
</tr>
<tr class="even">
<td><p><em>DismImageRepairable</em></p></td>
<td><p>1</p></td>
<td><p>The image is corrupted but can be repaired.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismImageNonRepairable</em></p></td>
<td><p>2</p></td>
<td><p>The image is corrupted and cannot be repaired. Discard the image and start again.</p></td>
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


[DismCheckImageHealth Function](dismcheckimagehealth-function.md)

[DismRestoreImageHealth Function](dismrestoreimagehealth-function.md)

 

 




