---
title: DismMountMode Enumeration
description: DismMountMode Enumeration
ms.assetid: aa14d860-bab5-475d-b243-95de5a3af9e5

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismMountMode
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismMountMode Enumeration


Specifies whether an image is mounted as read-only or as read-write.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismMountMode
{
    DismReadWrite = 0,
    DismReadOnly = 1
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
<td><p><em>DismReadWrite</em></p></td>
<td><p>0</p></td>
<td><p>Mounts an image in read-write mode.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReadOnly</em></p></td>
<td><p>1</p></td>
<td><p>Mounts an image in read-only mode.</p></td>
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


[DismMountedImageInfo Structure](dismmountedimageinfo-structure.md)

[DismMountImage Function](dismmountimage-function.md)

 

 




