---
title: Test Members
description: Test Members
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c77e045d-9511-4432-8a38-1975f4a99032


ms.date: 10/15/2017
ms.topic: article


---

# Test Members


The following table lists the members exposed by the [Test Class](test-class.md).

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
<td><p><a href="test-arefiltersapplied-property.md" data-raw-source="[AreFiltersApplied](test-arefiltersapplied-property.md)">AreFiltersApplied</a></p></td>
<td><p>Gets a value indicating whether filters have been applied for this result.</p></td>
</tr>
<tr class="even">
<td><p><a href="testexecutionstate-property.md" data-raw-source="[ExecutionState](testexecutionstate-property.md)">ExecutionState</a></p></td>
<td><p>Indicates whether there is an instance of this test that is queued, waiting to be run, or not running.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testinstanceid-property.md" data-raw-source="[InstanceId](testinstanceid-property.md)">InstanceId</a></p></td>
<td><p>Gets the instance Id.</p></td>
</tr>
<tr class="even">
<td><p><a href="test-manuallyadded-property.md" data-raw-source="[ManuallyAdded](test-manuallyadded-property.md)">ManuallyAdded</a></p></td>
<td><p>Gets whether the test was added separate from the feature detection process.</p></td>
</tr>
<tr class="odd">
<td><p><a href="teststatus-property.md" data-raw-source="[Status](teststatus-property.md)">Status</a></p></td>
<td><p>Gets the status of the test.</p></td>
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
<td><p><strong>LockObject</strong></p></td>
<td><p>(Inherited from <strong>NotificationBase</strong>)</p></td>
</tr>
</tbody>
</table>

 

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
<td><p><a href="test-addtests-method.md" data-raw-source="[AddTests](test-addtests-method.md)">AddTests</a></p></td>
<td>This method should not be called.
<div class="alert">
<strong>Warning</strong>  This functionality is being deprecated. Please use playlists to create custom test pass lists.
</div>
<div>
 
</div></td>
</tr>
<tr class="even">
<td><p><a href="testdeletetestresult-method.md" data-raw-source="[DeleteTestResult](testdeletetestresult-method.md)">DeleteTestResult</a></p></td>
<td><p>This method deletes a specific result.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="testfiltermultidevicetestgroups-method.md" data-raw-source="[FilterMultiDeviceTestGroups](testfiltermultidevicetestgroups-method.md)">FilterMultiDeviceTestGroups</a></p></td>
<td><p>This method removes tests from a list of tests that can be consolidated and returns the consolidated groupings of tests that are compatible.</p></td>
</tr>
<tr class="odd">
<td><p><a href="test-getdefaulttemplateparameters-method.md" data-raw-source="[GetDefaultTemplateParameters](test-getdefaulttemplateparameters-method.md)">GetDefaultTemplateParameters</a></p></td>
<td><p>Gets the template parameters with default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="testgetmachinerole-method.md" data-raw-source="[GetMachineRole](testgetmachinerole-method.md)">GetMachineRole</a></p></td>
<td><p>This method returns a logical Machine Set.</p></td>
</tr>
<tr class="even">
<td><p><a href="testgetparameters-method.md" data-raw-source="[GetParameters](testgetparameters-method.md)">GetParameters</a></p></td>
<td><p>This method retrieves a dictionary collection of test parameters, sorted by parameter name.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testgetrequirements-method.md" data-raw-source="[GetRequirements](testgetrequirements-method.md)">GetRequirements</a></p></td>
<td><p>This method retrieves the enumerable list of certification requirements that this test verifies.</p></td>
</tr>
<tr class="even">
<td><p><a href="testgetsupportedplatforms-method.md" data-raw-source="[GetSupportedPlatforms](testgetsupportedplatforms-method.md)">GetSupportedPlatforms</a></p></td>
<td><p>This method returns a enumerable list of the architectures supported by this certification test.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testgettestresults-method.md" data-raw-source="[GetTestResults](testgettestresults-method.md)">GetTestResults</a></p></td>
<td><p>This method retrieves the list of the test results generated during runs of this certification test.</p></td>
</tr>
<tr class="even">
<td><p><a href="testgettests-method.md" data-raw-source="[GetTests](testgettests-method.md)">GetTests</a></p></td>
<td><p>This method retrieves a test list.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testgettesttargets-method.md" data-raw-source="[GetTestTargets](testgettesttargets-method.md)">GetTestTargets</a></p></td>
<td><p>This method retrieves a list of possible test targets for this test.</p></td>
</tr>
<tr class="even">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="testqueuetest-method.md" data-raw-source="[QueueTest](testqueuetest-method.md)">QueueTest</a></p></td>
<td><p>Overloaded.</p></td>
</tr>
<tr class="even">
<td><p><a href="test-removetests-method.md" data-raw-source="[RemoveTests](test-removetests-method.md)">RemoveTests</a></p></td>
<td>This method should not be called.
<div class="alert">
<strong>Warning</strong>  This functionality is being deprecated. Please use playlists to create custom test pass lists.
</div>
<div>
 
</div></td>
</tr>
<tr class="odd">
<td><p><a href="testsetparameter-method.md" data-raw-source="[SetParameter](testsetparameter-method.md)">SetParameter</a></p></td>
<td><p>Overloaded.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToString</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
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
<td><p><strong>Finalize</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><strong>MemberwiseClone</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
</tbody>
</table>

 

 

 






