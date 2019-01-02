---
title: PackageManager Methods
description: PackageManager Methods
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bff068ce-2065-4fe0-92c3-867c7b37a7e4


ms.date: 10/15/2017
ms.topic: article


---

# PackageManager Methods


## <span id="Public_Methods"></span><span id="public_methods"></span><span id="PUBLIC_METHODS"></span>Public Methods


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

 

 

 






