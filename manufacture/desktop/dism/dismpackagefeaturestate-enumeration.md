---
title: DismPackageFeatureState Enumeration
description: DismPackageFeatureState Enumeration
ms.assetid: 0a21ef96-305a-4466-990c-628bd3291de3

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismPackageFeatureState
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismPackageFeatureState Enumeration


Specifies the state of a package or a feature.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismPackageFeatureState
{
    DismStateNotPresent = 0,
    DismStateUninstallPending = 1,
    DismStateStaged = 2,
    DismStateRemoved = 3,
    DismStateInstalled = 4,
    DismStateInstallPending = 5,
    DismStateSuperseded = 6,
    DismStatePartiallyInstalled = 7
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
<td><p><em>DismStateNotPresent</em></p></td>
<td><p>0</p></td>
<td><p>The package or feature is not present.</p></td>
</tr>
<tr class="even">
<td><p><em>DismStateUninstallPending</em></p></td>
<td><p>1</p></td>
<td><p>An uninstall process for the package or feature is pending. Additional processes are pending and must be completed before the package or feature is successfully uninstalled.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismStateStaged</em></p></td>
<td><p>2</p></td>
<td><p>The package or feature is staged.</p></td>
</tr>
<tr class="even">
<td><p><em>DismStateRemoved</em></p></td>
<td><p>3</p></td>
<td><p>Metadata about the package or feature has been added to the system, but the package or feature is not present.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismStateInstalled</em></p></td>
<td><p>4</p></td>
<td><p>The package or feature is installed.</p></td>
</tr>
<tr class="even">
<td><p><em>DismStateInstallPending</em></p></td>
<td><p>5</p></td>
<td><p>The install process for the package or feature is pending. Additional processes are pending and must be completed before the package or feature is successfully installed.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismStateSuperseded</em></p></td>
<td><p>6</p></td>
<td><p>The package or feature has been superseded by a more recent package or feature.</p></td>
</tr>
<tr class="even">
<td><p><em>DismStatePartiallyInstalled</em></p></td>
<td><p>7</p></td>
<td><p>The package or feature is partially installed. Some parts of the package or feature have not been installed.</p></td>
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


[DismPackage Structure](dismpackage-structure.md)

[DismPackageInfo Structure](dismpackageinfo-structure.md)

[DismFeature Structure](dismfeature-structure.md)

[DismFeatureInfo Structure](dismfeatureinfo-structure.md)

 

 




