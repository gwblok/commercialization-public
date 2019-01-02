---
title: DismEnableFeature function
description: Enables a feature in an image. Features are identified by a name and can optionally be tied to a package.
ms.assetid: 46e0febe-47c0-432c-9db6-1a15d108c5bc
keywords: DismEnableFeature function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismEnableFeature
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismEnableFeature function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Enables a feature in an image. Features are identified by a name and can optionally be tied to a package.

Syntax
---

```
HRESULT WINAPI DismEnableFeature(
  _In_     DismSession            Session,
  _In_     PCWSTR                 FeatureName,
  _In_opt_ PCWSTR                 Identifier,
  _In_opt_ DismPackageIdentifier  PackageIdentifier,
  _In_     BOOL                   LimitAccess,
  _In_opt_ PCWSTR                 *SourcePaths,
  _In_opt_ UINT                   SourcePathCount,
  _In_     BOOL                   EnableAll,
  _In_opt_ HANDLE                 CancelEvent,
  _In_opt_ DISM_PROGRESS_CALLBACK Progress,
  _In_opt_ PVOID                  UserData
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*FeatureName* \[in\]  
The name of the feature that is being enabled. To enable more than one feature, separate each feature name with a semicolon.

*Identifier* \[in, optional\]  
Optional. Either an absolute path to a .cab file or the package name for the parent package of the feature to be enabled.

*PackageIdentifier* \[in, optional\]  
Optional. A valid [DismPackageIdentifier](dismpackageidentifier-enumeration.md) enumeration value. *DismPackageName* should be used when the *Identifier* parameter is pointing to a package name, and *DismPackagePath* should be used when *Identifier* points to the absolute path of a .cab file. If *Identifier* field is not **NULL**, you must specify a valid *PackageIdentifier* parameter. If the *Identifier* field is **NULL**, the *PackageIdentifier* parameter is ignored.

*LimitAccess* \[in\]  
This parameter is ignored starting with Windows 8.1 and Windows Server 2012 R2.

**Windows 8 and Windows Server 2012:  **

A Boolean value indicating whether Windows Update (WU) should be contacted as a source location for downloading files if none are found in other specified locations. Before checking WU, DISM will check for the files in the *SourcePaths* provided and in any locations specified in the registry by group policy. If the files required to enable the feature are still present on the computer, this flag is ignored.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Do not check WU for repair files.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Default. Check WU for repair files.</p></td>
</tr>
</tbody>
</table>

 

*SourcePaths* \[in, optional\]  
This parameter is ignored starting with Windows 8.1 and Windows Server 2012 R2.

**Windows 8 and Windows Server 2012:  **

A list of source locations to check for files needed to enable the feature.

*SourcePathCount* \[in, optional\]  
This parameter is ignored starting with Windows 8.1 and Windows Server 2012 R2.

**Windows 8 and Windows Server 2012:  **

The number of source locations specified.

*EnableAll* \[in\]  
Enable all dependencies of the feature. If the specified feature or any one of its dependencies cannot be enabled, none of them will be changed from their existing state.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>Enable all dependencies of the feature.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>Only enable the specified feature.</p></td>
</tr>
</tbody>
</table>

 

*CancelEvent* \[in, optional\]  
Optional. You can set a *CancelEvent* for this function in order to cancel the operation in progress when signaled by the client. If the *CancelEvent* is received at a stage when the operation cannot be canceled, the operation will continue and return a success code. If the *CancelEvent* is received and the operation is canceled, the image state is unknown. You should verify the image state before continuing or discard the changes and start again.

*Progress* \[in, optional\]  
Optional. A pointer to a client-defined [*DismProgressCallback*](dismprogresscallback.md).

*UserData* \[in, optional\]  
Optional. User defined custom data.

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


If the feature is present in the foundation package, you do not have to specify any package information. If the feature is in an optional package or feature pack that has already been installed in the image, specify a package name in the *Identifier* parameter and specify *DismPackageName* as the *PackageIdentifier*.If the feature cannot be enabled due to the parent feature not being enabled, a special error code will be returned. You can use *EnableAll* to enable the parent features when you enable the specified features, or you can use the [**DismGetFeatureParent**](dismgetfeatureparent-function.md) to enumerate the parent features and enable them first.

**Important**  If the feature to be enabled is not a component of the foundation package, you must add the parent optional package with the [**DismAddPackage**](dismaddpackage-function.md) before you enable the feature. Do not you specify a path to a .cab file of an optional package that has not been added to the image in the *Identifier* parameter. If you specify a package that has not been added, and you specify *DismPackagePath* as the *PackageIdentifier*, the function will complete successfully but the feature will not be enabled.

 

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismEnableFeature(Session, “WindowsMediaPlayer”, NULL, PackageNone, TRUE, NULL, 0, FALSE, NULL, NULL, NULL);
```

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
<td><p>Windows 7, Windows Server 2008 R2, Windows PE 3.0, Windows 8, Windows Server 2012, Windows Preinstallation Environment (Windows PE) 4.0, Windows 8.1, Windows Server 2012 R2, Windows 10, Windows Server 2016</p>
<div class="alert">
<strong>Note</strong>  <em>LimitAccess</em>, <em>SourcePaths</em>, <em>SourcePathCount</em>, and <em>EnableAll</em> are only supported on Windows 8 and Windows Server 2012.
</div>
<div>
 
</div></td>
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
<tr class="even">
<td><p>Library</p></td>
<td>DismAPI.lib</td>
</tr>
<tr class="odd">
<td><p>DLL</p></td>
<td>DismAPI.dll</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismAddPackage**](dismaddpackage-function.md)

[**DismDisableFeature**](dismdisablefeature-function.md)

[**DismGetFeatures**](dismgetfeatures-function.md)

[**DismGetFeatureInfo**](dismgetfeatureinfo-function.md)

 

 




