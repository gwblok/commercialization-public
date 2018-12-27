---
title: DismPackageIdentifier Enumeration
description: DismPackageIdentifier Enumeration
ms.assetid: eeabc89d-70b0-4cd6-abf9-07cfd51cac87

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismPackageIdentifier
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismPackageIdentifier Enumeration


Specifies whether a package is identified by name or by file path.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismPackageIdentifier
{
    DismPackageNone = 0,
    DismPackageName = 1,
    DismPackagePath = 2
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
<td><p><em>DismPackageNone</em></p></td>
<td><p>0</p></td>
<td><p>No package is specified.</p></td>
</tr>
<tr class="even">
<td><p><em>DismPackageName</em></p></td>
<td><p>1</p></td>
<td><p>The package is identified by its name.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismPackagePath</em></p></td>
<td><p>2</p></td>
<td><p>The package is specified by its path.</p></td>
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


[DismRemovePackage Function](dismremovepackage-function.md)

[DismEnableFeature Function](dismenablefeature-function.md)

[DismGetPackageInfo Function](dismgetpackageinfo-function.md)

[DismGetFeatures Function](dismgetfeatures-function.md)

[DismGetFeatureInfo Function](dismgetfeatureinfo-function.md)

[DismGetFeatureParent Function](dismgetfeatureparent-function.md)

 

 




