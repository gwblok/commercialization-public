---
title: PackageManager Members
description: PackageManager Members
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3cf902ca-e04a-444b-ae5b-18028ab98893


ms.date: 10/15/2017
ms.topic: article


---

# PackageManager Members


The following table lists the members exposed by the [PackageManager Class](packagemanager-class.md).

## <span id="Public_Constructors"></span><span id="public_constructors"></span><span id="PUBLIC_CONSTRUCTORS"></span>Public Constructors


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PackageManager(String)</p></td>
<td><p>Overloaded.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Public_Fields"></span><span id="public_fields"></span><span id="PUBLIC_FIELDS"></span>Public Fields


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="packagemanagerpackageversionstring-field.md" data-raw-source="[PackageVersionString](packagemanagerpackageversionstring-field.md)">PackageVersionString</a></p></td>
<td><p>The version (string) for the package version that this <strong>PackageManager</strong> can open.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanager-winblueversion-field.md" data-raw-source="[WinBlueVersion](packagemanager-winblueversion-field.md)">WinBlueVersion</a></p></td>
<td><p>Specifies the version for packages created for WinBlue.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanager-win8version-field.md" data-raw-source="[Win8Version](packagemanager-win8version-field.md)">Win8Version</a></p></td>
<td><p>Specifies the version for packages created for Win8 (HCK 2.0).</p></td>
</tr>
<tr class="even">
<td><p><a href="winthresholdandredstoneversion-field.md" data-raw-source="[WinThresholdAndRedstoneVersion](winthresholdandredstoneversion-field.md)">WinThresholdAndRedstoneVersion</a></p></td>
<td><p>Specifies the version for packages created for Windows 10.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagedownlevelversions-field.md" data-raw-source="[PackageDownlevelVersions](packagedownlevelversions-field.md)">PackageDownlevelVersions</a></p></td>
<td><p>A list of downlevel versions that packages can target.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Public_Properties"></span><span id="public_properties"></span><span id="PUBLIC_PROPERTIES"></span>Public Properties


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Certificate</strong></p></td>
<td><p>This property represents the certificate used to sign a submission package. This property will be <strong>null</strong> if the package is not signed.</p></td>
</tr>
<tr class="even">
<td><p>ConnectionType</p></td>
<td><p>Overridden. This property represents the connection type for this submission package.</p></td>
</tr>
<tr class="odd">
<td><p>FileName</p></td>
<td><p>This property represents the filename of the submission package that was opened.</p></td>
</tr>
<tr class="even">
<td><p>PackageVersion</p></td>
<td><p>This property represents the package version that this instance of <strong>PackageManager</strong> is able to read.</p></td>
</tr>
<tr class="odd">
<td><p>Version</p></td>
<td><p>This property represents the major version of the Windows HCK Controller. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
<tr class="even">
<td><p>VersionString</p></td>
<td><p>This property represents the version of the Windows HCK Controller and its content. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
</tbody>
</table>

 

## <span id="Protected_Properties"></span><span id="protected_properties"></span><span id="PROTECTED_PROPERTIES"></span>Protected Properties


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IsDisposed</p></td>
<td><p>This property represents a value indicating whether this object has already freed its resources. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
</tbody>
</table>

 

## <span id="Public_Methods"></span><span id="public_methods"></span><span id="PUBLIC_METHODS"></span>Public Methods


### <span id="Public_Methods"></span><span id="public_methods"></span><span id="PUBLIC_METHODS"></span>Public Methods

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="packagemanagercreatedevicefamily-method.md" data-raw-source="[CreateDeviceFamily](packagemanagercreatedevicefamily-method.md)">CreateDeviceFamily</a></p></td>
<td><p>Overridden. This method creates a new device family to use.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagercreateproject-method.md" data-raw-source="[CreateProject](packagemanagercreateproject-method.md)">CreateProject</a></p></td>
<td><p>Overridden. This method creates a new project within the submission package.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagerdeletedevicefamily-method.md" data-raw-source="[DeleteDeviceFamily](packagemanagerdeletedevicefamily-method.md)">DeleteDeviceFamily</a></p></td>
<td><p>Overridden. This method deletes a device family.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagerdeleteproject-method.md" data-raw-source="[DeleteProject](packagemanagerdeleteproject-method.md)">DeleteProject</a></p></td>
<td><p>Overridden. This method deletes a project from the submission package.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagerextractdriverpackages-method.md" data-raw-source="[ExtractDriverPackages](packagemanagerextractdriverpackages-method.md)">ExtractDriverPackages</a></p></td>
<td><p>This method extracts all the driver packages linked with a submission package.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagerextractsupplementalfiles-method.md" data-raw-source="[ExtractSupplementalFiles](packagemanagerextractsupplementalfiles-method.md)">ExtractSupplementalFiles</a></p></td>
<td><p>This method extracts all the &quot;supplemental files&quot; linked with a submission package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetdevicefamilies-method.md" data-raw-source="[GetDeviceFamilies](packagemanagergetdevicefamilies-method.md)">GetDeviceFamilies</a></p></td>
<td><p>Overridden. This method retrieves a list of all of the device families used in this submission package.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagergetfeatures-method.md" data-raw-source="[GetFeatures](packagemanagergetfeatures-method.md)">GetFeatures</a></p></td>
<td><p>Overridden. This method retrieves the features found within the submission package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetfilters-method.md" data-raw-source="[GetFilters](packagemanagergetfilters-method.md)">GetFilters</a></p></td>
<td><p>Overridden. This method retrieves the filters present in the submission package. Getting filters from a package is not supported.</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetplatforms-method.md" data-raw-source="[GetPlatforms](packagemanagergetplatforms-method.md)">GetPlatforms</a></p></td>
<td><p>Gets a collection of all platforms.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagergetproducttypes-method.md" data-raw-source="[GetProductTypes](packagemanagergetproducttypes-method.md)">GetProductTypes</a></p></td>
<td><p>Overridden. This method retrieves the product types found within the package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetproject-method.md" data-raw-source="[GetProject](packagemanagergetproject-method.md)">GetProject</a></p></td>
<td><p>Overridden. This method retrieves a Submission from the package that matches projectName.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanager-getprojectinfo-method.md" data-raw-source="[GetProjectInfo](packagemanager-getprojectinfo-method.md)">GetProjectInfo</a></p></td>
<td><p>Gets the <a href="projectinfo-class.md" data-raw-source="[ProjectInfo Class](projectinfo-class.md)">ProjectInfo Class</a> for a specific project.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetprojectinfolist-method.md" data-raw-source="[GetProjectInfoList](packagemanagergetprojectinfolist-method.md)">GetProjectInfoList</a></p></td>
<td><p>Overridden. This method retrieves a list containing one ProjectInfo object per Project found in the submission package.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagergetprojectnames-method.md" data-raw-source="[GetProjectNames](packagemanagergetprojectnames-method.md)">GetProjectNames</a></p></td>
<td><p>Overridden. This method retrieves a list of names for projects stored in this package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetprojectsummary-method.md" data-raw-source="[GetProjectSummary](packagemanagergetprojectsummary-method.md)">GetProjectSummary</a></p></td>
<td><p>Gets a collection of ProjectSummary objects for all the projects.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagemanagergetrequirements-method.md" data-raw-source="[GetRequirements](packagemanagergetrequirements-method.md)">GetRequirements</a></p></td>
<td><p>Overridden. This method retrieves the requirements found within the submission package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagergetrootmachinepool-method.md" data-raw-source="[GetRootMachinePool](packagemanagergetrootmachinepool-method.md)">GetRootMachinePool</a></p></td>
<td><p>Overridden. This method retrieves the root machine pool for this package.</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagersign-method.md" data-raw-source="[Sign](packagemanagersign-method.md)">Sign</a></p></td>
<td><p>Sign an existing package.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToString</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="packagemanagerverifysignature-method.md" data-raw-source="[VerifySignature](packagemanagerverifysignature-method.md)">VerifySignature</a></p></td>
<td><p>This method is no longer valid. Use <strong>IOpcFactory</strong> and <strong>CreateDigitalSignatureManager</strong> to detect signatures.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Protected_Methods"></span><span id="protected_methods"></span><span id="PROTECTED_METHODS"></span>Protected Methods


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="packagemanagerdispose-method.md" data-raw-source="[Dispose](packagemanagerdispose-method.md)">Dispose</a></p></td>
<td><p>This method implements the IDisposable interface. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
<tr class="even">
<td><p><strong>Finalize</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><strong>MemberwiseClone</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
</tbody>
</table>

 

 

 






