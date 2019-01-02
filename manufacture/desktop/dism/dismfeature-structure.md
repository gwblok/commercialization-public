---
title: DismFeature structure
description: Describes basic information about a feature, such as the feature name and feature state.
ms.assetid: 43347e6a-ed58-4dcf-9a8c-e9e9017a582e
keywords: DismFeature structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismFeature
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismFeature structure


Describes basic information about a feature, such as the feature name and feature state.

Syntax
---

```
typedef struct _DismFeature {
  PCWSTR                  FeatureName;
  DismPackageFeatureState State;
} DismFeature;
```

Members
----

**FeatureName**  
The name of the feature.

**State**  
A valid [DismPackageFeatureState](dismpackagefeaturestate-enumeration.md) enumeration value such as **DismStateInstalled**.

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

## <span id="see_also"></span>See also


[DismPackageFeatureState](dismpackagefeaturestate-enumeration.md)

[DismPackageInfo](dismpackageinfo-structure.md)

[**DismGetFeatures**](dismgetfeatures-function.md)

[**DismGetFeatureParent**](dismgetfeatureparent-function.md)

 

 




