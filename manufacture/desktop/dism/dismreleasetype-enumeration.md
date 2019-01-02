---
title: DismReleaseType Enumeration
description: DismReleaseType Enumeration
ms.assetid: f6ba949a-ed77-43f3-bf1e-830927aa67a5

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismReleaseType
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismReleaseType Enumeration


Specifies the release type of a package.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismReleaseType
{
    DismReleaseTypeCriticalUpdate = 0,
    DismReleaseTypeDriver = 1,
    DismReleaseTypeFeaturePack = 2,
    DismReleaseTypeHotfix = 3,
    DismReleaseTypeSecurityUpdate = 4,
    DismReleaseTypeSoftwareUpdate = 5,
    DismReleaseTypeUpdate = 6,
    DismReleaseTypeUpdateRollup = 7,
    DismReleaseTypeLanguagePack = 8,
    DismReleaseTypeFoundation = 9,
    DismReleaseTypeServicePack = 10,
    DismReleaseTypeProduct = 11,
    DismReleaseTypeLocalPack = 12,
    DismReleaseTypeOther = 13,
    DismReleaseTypeOnDemandPack = 14
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
<td><p><em>DismReleaseTypeCriticalUpdate</em></p></td>
<td><p>0</p></td>
<td><p>The package is a critical update.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeDriver</em></p></td>
<td><p>1</p></td>
<td><p>The package is a driver.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeFeaturePack</em></p></td>
<td><p>2</p></td>
<td><p>The package is a feature pack.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeHotfix</em></p></td>
<td><p>3</p></td>
<td><p>The package is a hotfix.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeSecurityUpdate</em></p></td>
<td><p>4</p></td>
<td><p>The package is a security update.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeSoftwareUpdate</em></p></td>
<td><p>5</p></td>
<td><p>The package is a software update.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeUpdate</em></p></td>
<td><p>6</p></td>
<td><p>The package is a general update.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeUpdateRollup</em></p></td>
<td><p>7</p></td>
<td><p>The package is an update rollup.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeLanguagePack</em></p></td>
<td><p>8</p></td>
<td><p>The package is a language pack.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeFoundation</em></p></td>
<td><p>9</p></td>
<td><p>The package is a foundation package.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeServicePack</em></p></td>
<td><p>10</p></td>
<td><p>The package is a service pack.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeProduct</em></p></td>
<td><p>11</p></td>
<td><p>The package is a product release.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeLocalPack</em></p></td>
<td><p>12</p></td>
<td><p>The package is a local pack.</p></td>
</tr>
<tr class="even">
<td><p><em>DismReleaseTypeOther</em></p></td>
<td><p>13</p></td>
<td><p>The package is another type of release.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismReleaseTypeOnDemandPack</em></p></td>
<td><p>14</p></td>
<td><p>This package is a feature on demand.</p></td>
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


[DismPackage Structure](dismpackage-structure.md)

[DismPackageInfo Structure](dismpackageinfo-structure.md)

 

 




