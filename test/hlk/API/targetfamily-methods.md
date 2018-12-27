---
title: TargetFamily Methods
description: TargetFamily Methods
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c781c7aa-cc60-4a48-ba7a-f9e8d424d2fa


ms.date: 10/15/2017
ms.topic: article


---

# TargetFamily Methods


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
<td><p><a href="targetfamily-addtests-method.md" data-raw-source="[AddTests](targetfamily-addtests-method.md)">AddTests</a></p></td>
<td>Adds the given Tests to this <a href="targetfamily-class.md" data-raw-source="[TargetFamily](targetfamily-class.md)">TargetFamily</a>.
<div class="alert">
<strong>Warning</strong>  This functionality is being deprecated. Please use playlists to create custom test pass lists.
</div>
<div>
 
</div></td>
</tr>
<tr class="even">
<td><p><a href="targetfamilycreatetarget-method.md" data-raw-source="[CreateTarget](targetfamilycreatetarget-method.md)">CreateTarget</a></p></td>
<td>Creates a target from a <strong>TargetData</strong> object, and adds it to a target family.
<div class="alert">
<strong>Warning</strong>  Some overloads of this method are being deprecated. Please use <a href="targetfamilycreatetarget-method--ienumerable-.md" data-raw-source="[CreateTarget(IEnumerable&amp;lt;TargetData&amp;gt;)](targetfamilycreatetarget-method--ienumerable-.md)">CreateTarget(IEnumerable&lt;TargetData&gt;)</a>.
</div>
<div>
 
</div></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamilydeletetarget-method.md" data-raw-source="[DeleteTarget](targetfamilydeletetarget-method.md)">DeleteTarget</a></p></td>
<td><p>This method deletes a test target from a target family.</p></td>
</tr>
<tr class="even">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamilygetfeatures-method.md" data-raw-source="[GetFeatures](targetfamilygetfeatures-method.md)">GetFeatures</a></p></td>
<td><p>This method retrieves a list of features for this <strong>TargetFamily</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamilygettargets-method.md" data-raw-source="[GetTargets](targetfamilygettargets-method.md)">GetTargets</a></p></td>
<td><p>This method retrieves a list of test targets that have been assigned to this Device Family.</p></td>
</tr>
<tr class="even">
<td><p><a href="targetfamilygettestresults-method.md" data-raw-source="[GetTestResults](targetfamilygettestresults-method.md)">GetTestResults</a></p></td>
<td><p>This method retrieves a list of results for this <strong>TargetFamily</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamilygettests-method.md" data-raw-source="[GetTests](targetfamilygettests-method.md)">GetTests</a></p></td>
<td><p>This method retrieves a list of all of the tests needed for this <strong>TargetFamily</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamilyisvalidtarget-method.md" data-raw-source="[IsValidTarget](targetfamilyisvalidtarget-method.md)">IsValidTarget</a></p></td>
<td><p>Checks to see if the TargetData can be a member of this target family.</p></td>
</tr>
<tr class="even">
<td><p><a href="targetfamilyqueuetest-method.md" data-raw-source="[QueueTest](targetfamilyqueuetest-method.md)">QueueTest</a></p></td>
<td><p>Overloaded.</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamily-removetests-method.md" data-raw-source="[RemoveTests](targetfamily-removetests-method.md)">RemoveTests</a></p></td>
<td>Removes the given Tests from this <a href="targetfamily-class.md" data-raw-source="[TargetFamily](targetfamily-class.md)">TargetFamily</a>.
<div class="alert">
<strong>Warning</strong>  This functionality is being deprecated. Please use playlists to create custom test pass lists.
</div>
<div>
 
</div></td>
</tr>
<tr class="even">
<td><p><a href="targetfamilysetcommonparameters-method.md" data-raw-source="[SetCommonParameters](targetfamilysetcommonparameters-method.md)">SetCommonParameters</a></p></td>
<td><p>This method sets all of the parameters with a given name to the same value for all child jobs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="targetfamliytargetsarevalidinsametargetfamily-method.md" data-raw-source="[TargetsAreValidInSameTargetFamily](targetfamliytargetsarevalidinsametargetfamily-method.md)">TargetsAreValidInSameTargetFamily</a></p></td>
<td><p>This method checks to see if the two <a href="targetdata-class.md" data-raw-source="[TargetData](targetdata-class.md)">TargetData</a> objects can be members of the same target family.</p></td>
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
<td><p><strong>Family</strong></p></td>
<td><p>This property represents the <strong>DeviceFamily</strong> object associated with this <strong>TargetFamily</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsValid</strong></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ProductInstance</strong></p></td>
<td><p>This property represents the <strong>ProductInstance</strong> parent object of this <strong>TargetFamily</strong>.</p></td>
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

 

 

 






