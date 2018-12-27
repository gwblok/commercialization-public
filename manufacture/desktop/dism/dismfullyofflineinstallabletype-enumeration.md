---
title: DismFullyOfflineInstallableType Enumeration
description: DismFullyOfflineInstallableType Enumeration
ms.assetid: 672b270d-7a78-4797-80d2-d350c238b8cd

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismFullyOfflineInstallableType
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismFullyOfflineInstallableType Enumeration


Specifies whether a package can be installed to an offline image without booting the image.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismFullyOfflineInstallable
{
    DismFullyOfflineInstallable = 0,
    DismFullyOfflineNotInstallable = 1,
    DismFullyOfflineInstallableUndetermined = 2
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
<td><p><em>DismFullyOfflineInstallable</em></p></td>
<td><p>0</p></td>
<td><p>The package can be installed to an offline image without booting the image.</p></td>
</tr>
<tr class="even">
<td><p><em>DismFullyOfflineNotInstallable</em></p></td>
<td><p>1</p></td>
<td><p>You must boot into the image in order to complete installation of this package.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismFullyOfflineInstallableUndetermined</em></p></td>
<td><p>0</p></td>
<td><p>You may have to boot the image in order to complete the installation of this package.</p></td>
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


[DismGetPackageInfo Function](dismgetpackageinfo-function.md)

[DismPackageInfo Structure](dismpackageinfo-structure.md)

 

 




