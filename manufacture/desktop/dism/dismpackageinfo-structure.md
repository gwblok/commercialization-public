---
title: DismPackageInfo structure
description: Describes detailed package information such as the client used to install the package, the date and time that the package was installed, and support information.
ms.assetid: e52cd827-11e0-43c2-8f4a-ecc3cbc14585
keywords: DismPackageInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismPackageInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismPackageInfo structure


Describes detailed package information such as the client used to install the package, the date and time that the package was installed, and support information.

Syntax
---

```
typedef struct _DismPackageInfo {
  PCWSTR                          PackageName;
  DismPackageFeatureState         PackageState;
  DismReleaseType                 ReleaseType;
  SYSTEMTIME                      InstallTime;
  BOOL                            Applicable;
  PCWSTR                          Copyright;
  PCWSTR                          Company;
  SYSTEMTIME                      CreationTime;
  PCWSTR                          DisplayName;
  PCWSTR                          Description;
  PCWSTR                          InstallClient;
  PCWSTR                          InstallPackageName;
  SYSTEMTIME                      LastUpdateTime;
  PCWSTR                          ProductName;
  PCWSTR                          ProductVersion;
  DismRestartType                 RestartRequired;
  DismFullyOfflineInstallableType FullyOffline;
  PCWSTR                          SupportInformation;
  DismCustomProperty              *CustomProperty;
  UINT                            CustomPropertyCount;
  DismFeature                     *Feature;
  UINT                            FeatureCount;
} DismPackageInfo;
```

Members
----

**PackageName**  
The name of the package.

**PackageState**  
A [DismPackageFeatureState](dismpackagefeaturestate-enumeration.md) enumeration value such as **DismStateResolved**.

**ReleaseType**  
A [DismReleaseType](dismreleasetype-enumeration.md) enumeration value such as **DismReleaseTypeUpdate**.

**InstallTime**  
The date and time that the package was installed. This field is local time, based on the servicing host computer.

**Applicable**  
**TRUE** if the package is applicable to the image, otherwise **FALSE**.

**Copyright**  
The copyright information of the package.

**Company**  
The company that released the package.

**CreationTime**  
The date and time that the package was created. This field is local time, based on the time zone of the computer that created the package.

**DisplayName**  
The display name of the package.

**Description**  
A description of the purpose of the package.

**InstallClient**  
The client that installed this package.

**InstallPackageName**  
The client that installed this package.

**LastUpdateTime**  
The date and time when this package was last updated. This field is local time, based on the servicing host computer.

**ProductName**  
The product name for this package.

**ProductVersion**  
The product version for this package.

**RestartRequired**  
A [DismRestartType](dismrestarttype-enumeration.md) enumeration value describing whether a restart is required after installing the package on an online image.

**FullyOffline**  
A [DismFullyOfflineInstallableType](dismfullyofflineinstallabletype-enumeration.md) enumeration value describing whether a package can be installed offline without booting the image.

**SupportInformation**  
A string listing additional support information for this package.

**CustomProperty**  
An array of [**DismCustomProperty**](dismcustomproperty-structure.md) structures representing the custom properties of the package.

**CustomPropertyCount**  
The number of elements in the *CustomProperty* array.

**Feature**  
An array of [**DismFeature**](dismfeature-structure.md) structures representing the features in the package.

**FeatureCount**  
The number of elements in the *Feature* array.

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

[DismReleaseType](dismreleasetype-enumeration.md)

[DismRestartType](dismrestarttype-enumeration.md)

[DismFullyOfflineInstallableType](dismfullyofflineinstallabletype-enumeration.md)

[**DismCustomProperty**](dismcustomproperty-structure.md)

[**DismFeature**](dismfeature-structure.md)

[**DismGetPackageInfo**](dismgetpackageinfo-function.md)

 

 




