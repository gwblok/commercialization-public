---
title: DatabaseProjectManager Methods
description: DatabaseProjectManager Methods
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 75448edb-8e21-4779-b40f-d35f34fef4f3


ms.date: 10/15/2017
ms.topic: article


---

# DatabaseProjectManager Methods


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
<td><p><a href="databaseprojectmanagercreatedevicefamily-method.md" data-raw-source="[CreateDeviceFamily](databaseprojectmanagercreatedevicefamily-method.md)">CreateDeviceFamily</a></p></td>
<td><p>Overridden. This method creates a new device family with the given name.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagercreateproject-method.md" data-raw-source="[CreateProject](databaseprojectmanagercreateproject-method.md)">CreateProject</a></p></td>
<td><p>Overridden. This method creates a new Project and adds it to the project collection.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagerdeletedevicefamily-method.md" data-raw-source="[DeleteDeviceFamily](databaseprojectmanagerdeletedevicefamily-method.md)">DeleteDeviceFamily</a></p></td>
<td><p>Overridden. This method deletes a named Device Family.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagerdeleteproject-method.md" data-raw-source="[.DeleteProject](databaseprojectmanagerdeleteproject-method.md)">.DeleteProject</a></p></td>
<td><p>Overridden. This method deletes a named project.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagerdispose-method.md" data-raw-source="[Dispose](databaseprojectmanagerdispose-method.md)">Dispose</a></p></td>
<td><p>This method implements the IDisposable interface. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
<tr class="even">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagergetdevicefamilies-method.md" data-raw-source="[GetDeviceFamilies](databaseprojectmanagergetdevicefamilies-method.md)">GetDeviceFamilies</a></p></td>
<td><p>Overridden. This method retrieves a list of available DeviceFamilies.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetfeatures-method.md" data-raw-source="[GetFeatures](databaseprojectmanagergetfeatures-method.md)">GetFeatures</a></p></td>
<td><p>Overridden. This method features all of the features stored in the Windows HCK.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagergetfilters-method.md" data-raw-source="[GetFilters](databaseprojectmanagergetfilters-method.md)">GetFilters</a></p></td>
<td><p>Overridden. This method returns all the filters installed in the system.</p></td>
</tr>
<tr class="even">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanager-getnetbiosname-method.md" data-raw-source="[GetNetBiosName](databaseprojectmanager-getnetbiosname-method.md)">GetNetBiosName</a></p></td>
<td><p>Converts a FQDN name to a NetBIOS name.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetplatforms-method.md" data-raw-source="[GetPlatforms](databaseprojectmanagergetplatforms-method.md)">GetPlatforms</a></p></td>
<td><p>Overridden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagergetproducttypes-method.md" data-raw-source="[GetProductTypes](databaseprojectmanagergetproducttypes-method.md)">GetProductTypes</a></p></td>
<td><p>Overridden.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetproject-method.md" data-raw-source="[GetProject](databaseprojectmanagergetproject-method.md)">GetProject</a></p></td>
<td><p>Overridden. This method loads an existing project into the collection.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanager-getprojectinfo-method.md" data-raw-source="[GetProjectInfo](databaseprojectmanager-getprojectinfo-method.md)">GetProjectInfo</a></p></td>
<td><p>Gets the <a href="projectinfo-class.md" data-raw-source="[ProjectInfo Class](projectinfo-class.md)">ProjectInfo Class</a> for a specific project.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetprojectinfolist-method.md" data-raw-source="[GetProjectInfoList](databaseprojectmanagergetprojectinfolist-method.md)">GetProjectInfoList</a></p></td>
<td><p>Overridden. This method retrieves a list of project information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagergetprojectnames-method.md" data-raw-source="[GetProjectNames](databaseprojectmanagergetprojectnames-method.md)">GetProjectNames</a></p></td>
<td><p>Overridden. This method retrieves a list of project names.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetprojectsummary-method.md" data-raw-source="[GetProjectSummary](databaseprojectmanagergetprojectsummary-method.md)">GetProjectSummary</a></p></td>
<td><p>Overridden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="databaseprojectmanagergetrequirements-method.md" data-raw-source="[GetRequirements](databaseprojectmanagergetrequirements-method.md)">GetRequirements</a></p></td>
<td><p>Overridden. This method retrieves the list of requirements in the Windows HCK.</p></td>
</tr>
<tr class="even">
<td><p><a href="databaseprojectmanagergetrootmachinepool-method.md" data-raw-source="[GetRootMachinePool](databaseprojectmanagergetrootmachinepool-method.md)">GetRootMachinePool</a></p></td>
<td><p>Overridden. This method retrieves the root machine pool.</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from Object)</p></td>
</tr>
<tr class="even">
<td><p><strong>ToString</strong></p></td>
<td><p>(Inherited from Object)</p></td>
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
<td><p>Dispose</p></td>
<td><p>Overridden. This method implements the <strong>IDisposable</strong> interface.</p></td>
</tr>
<tr class="even">
<td><p><strong>Finalize</strong></p></td>
<td><p>This method finalizes an instance of the <strong>ProjectManager</strong> class. (Inherited from <a href="projectmanager-class.md" data-raw-source="[ProjectManager Class](projectmanager-class.md)">ProjectManager Class</a>)</p></td>
</tr>
<tr class="odd">
<td><p><strong>MemberwiseClone</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
</tbody>
</table>

 

 

 






