---
title: TestResult Members
description: TestResult Members
MS-HAID:
- 'bd07c4c0-73e3-4401-92df-1f1d6cf2dac4'
- 'p\_hlk\_om.testresult\_members'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d78399bc-9ed7-4f13-9717-1eb37831794c


ms.date: 10/15/2017
ms.topic: article


---

# TestResult Members


The following table lists the members exposed by the [TestResult Class](testresult-class.md).

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
<td><p><a href="testresult-arefiltersapplied-property.md" data-raw-source="[AreFiltersApplied](testresult-arefiltersapplied-property.md)">AreFiltersApplied</a></p></td>
<td><p>Indicates whether filters have been applied for this result.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultcompletiontime-property.md" data-raw-source="[CompletionTime](testresultcompletiontime-property.md)">CompletionTime</a></p></td>
<td><p>This property represents the time when the corresponding certification test completed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresult-hasbugchecked-property.md" data-raw-source="[HasBugchecked](testresult-hasbugchecked-property.md)">HasBugchecked</a></p></td>
<td><p>Indicates whether a bugcheck occurred on the client machine during the test run.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultinstanceid-property.md" data-raw-source="[InstanceId](testresultinstanceid-property.md)">InstanceId</a></p></td>
<td><p>This property represents the instance ID value of the test result.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresult-ismultidevice-property.md" data-raw-source="[IsMultiDevice](testresult-ismultidevice-property.md)">IsMultiDevice</a></p></td>
<td><p>Indicates whether the test ran as a MultiDevice test.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultmachine-property.md" data-raw-source="[Machine](testresultmachine-property.md)">Machine</a></p></td>
<td><p>This property represents the machine (test computer) on which this test ran.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresultscheduletime-property.md" data-raw-source="[ScheduleTime](testresultscheduletime-property.md)">ScheduleTime</a></p></td>
<td><p>This property represents the time when the corresponding logo test was first scheduled.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultstarttime-property.md" data-raw-source="[StartTime](testresultstarttime-property.md)">StartTime</a></p></td>
<td><p>This property represents the time when the corresponding certification test was started and this result was generated.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresultstatus-property.md" data-raw-source="[Status](testresultstatus-property.md)">Status</a></p></td>
<td><p>This property represents the status of this certification test result.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresulttarget-property.md" data-raw-source="[Target](testresulttarget-property.md)">Target</a></p></td>
<td><p>This property represents the test target that this test result was obtained from.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresulttest-property.md" data-raw-source="[Test](testresulttest-property.md)">Test</a></p></td>
<td><p>This property represents the certification test object this result is generated for.</p></td>
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
<td><p><a href="testresultcancel-method.md" data-raw-source="[Cancel](testresultcancel-method.md)">Cancel</a></p></td>
<td><p>This method cancels a job that is scheduled.</p></td>
</tr>
<tr class="even">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresult-getalltests-method.md" data-raw-source="[GetAllTests](testresult-getalltests-method.md)">GetAllTests</a></p></td>
<td><p>Returns all tests consolidated for multi-device tests.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultgetappliedfilters-method.md" data-raw-source="[GetAppliedFilters](testresultgetappliedfilters-method.md)">GetAppliedFilters</a></p></td>
<td><p>This method retrieves the filters applied for this test result.</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultgetlogs-method.md" data-raw-source="[GetLogs](testresultgetlogs-method.md)">GetLogs</a></p></td>
<td><p>This method retrieves all of the logs associated with this test result.</p></td>
</tr>
<tr class="odd">
<td><p><a href="testresultgetparameters-method.md" data-raw-source="[GetParameters](testresultgetparameters-method.md)">GetParameters</a></p></td>
<td><p>This method retrieves the parameters that were applied to a test when it was run.</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultgettasks-method.md" data-raw-source="[GetTasks](testresultgettasks-method.md)">GetTasks</a></p></td>
<td><p>This method retrieves the tasks associated with this test.</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="testresultrefresh-method.md" data-raw-source="[Refresh](testresultrefresh-method.md)">Refresh</a></p></td>
<td><p>Refresh the current status of the result.</p></td>
</tr>
<tr class="odd">
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

 

 

 






