---
title: DismFeatureInfo structure
description: Describes advanced feature information, such as installed state and whether a restart is required after installation.
ms.assetid: 746e08db-8de8-4a7a-b5b6-065979c76e56
keywords: DismFeatureInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismFeatureInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismFeatureInfo structure


Describes advanced feature information, such as installed state and whether a restart is required after installation.

Syntax
---

```
typedef struct _DismFeatureInfo {
  PCWSTR                  FeatureName;
  DismPackageFeatureState FeatureState;
  PCWSTR                  DisplayName;
  PCWSTR                  Description;
  DismRestartType         RestartRequired;
  DismCustomProperty      *CustomProperty;
  UINT                    CustomPropertyCount;
} DismFeatureInfo;
```

Members
----

**FeatureName**  
The name of the feature.

**FeatureState**  
A valid [DismPackageFeatureState](dismpackagefeaturestate-enumeration.md) enumeration value such as **DismStateInstalled**.

**DisplayName**  
The display name of the feature. This is not always unique across all features.

**Description**  
The description of the feature.

**RestartRequired**  
A [DismRestartType](dismrestarttype-enumeration.md) enumeration value such as **DismRestartPossible**.

**CustomProperty**  
An array of [**DismCustomProperty**](dismcustomproperty-structure.md) structures.

**CustomPropertyCount**  
The number of elements in the *CustomProperty* array.

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


[**DismGetFeatureInfo**](dismgetfeatureinfo-function.md)

 

 




