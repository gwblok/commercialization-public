---
title: PackageWriter Members
description: PackageWriter Members
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a98f4773-89a7-4cdc-8f0e-d9b33dbe9045


ms.date: 10/15/2017
ms.topic: article


---

# PackageWriter Members


The following table lists the members exposed by the [PackageWriter Class](packagewriter-class.md).

## <span id="Public_Constructors"></span><span id="public_constructors"></span><span id="PUBLIC_CONSTRUCTORS"></span>Public Constructors


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>PackageWriter</p></td>
<td><p>Overloaded.</p></td>
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
<td><p><strong>PackageVersion</strong></p></td>
<td><p>This property represents the version of the package that this instance of <strong>PackageWriter</strong> will create.</p></td>
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
<td><p><a href="packagewriteradddriver-method.md" data-raw-source="[AddDriver](packagewriteradddriver-method.md)">AddDriver</a></p></td>
<td><p>This method adds driver files to the submission package and checks the driver files for driver signability. This method can only be used for submission packages. It cannot be used for update packages. The signability tests are done when drivers are added to the package. If the signability tests fail the driver is not added to the package. Down level operating system signability tests are automatically run. Errors from these signability results will not prevent submission creation (will not cause a false return value).The error messages for down level operating system signability runs will be captured and returned as warnings.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagewriteraddreplacementdriver-method.md" data-raw-source="[AddReplacementDriver](packagewriteraddreplacementdriver-method.md)">AddReplacementDriver</a></p></td>
<td><p>This method replaces a driver in the submission package. This method can only be used for update packages.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagewriteraddsupplementalfiles-method.md" data-raw-source="[AddSupplementalFiles](packagewriteraddsupplementalfiles-method.md)">AddSupplementalFiles</a></p></td>
<td><p>This method adds all of the files in a specified directory to a submission package. This method can be used for both submission packages and update packages.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagewriterdispose-method.md" data-raw-source="[Dispose](packagewriterdispose-method.md)">Dispose</a></p></td>
<td><p>Overloaded.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="packagewritermerge-method.md" data-raw-source="[Merge](packagewritermerge-method.md)">Merge</a></p></td>
<td><p>This method merges a project into an existing package. This method can only be used for existing submission packages.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagewritersave-method.md" data-raw-source="[Save](packagewritersave-method.md)">Save</a></p></td>
<td><p>Overloaded. This class contains methods used to save a submission package.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagewriter-savepartialpackage-method.md" data-raw-source="[SavePartialPackage](packagewriter-savepartialpackage-method.md)">SavePartialPackage</a></p></td>
<td><p>Overloaded.</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagewritersetprogressactionhandler-method.md" data-raw-source="[SetProgressActionHandler](packagewritersetprogressactionhandler-method.md)">SetProgressActionHandler</a></p></td>
<td><p>This method sets an action handler that is used to send out submission progress updates. This method can be used for both submission packages and update packages.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToString</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="packagewriter-targetfamiliesaredeepmergecompatible-method.md" data-raw-source="[TargetFamiliesAreDeepMergeCompatible](packagewriter-targetfamiliesaredeepmergecompatible-method.md)">TargetFamiliesAreDeepMergeCompatible</a></p></td>
<td><p>Checks if two target families are similar enough for deep merging.</p></td>
</tr>
<tr class="even">
<td><p><a href="packagewritervalidatemerge-method.md" data-raw-source="[ValidateMerge](packagewritervalidatemerge-method.md)">ValidateMerge</a></p></td>
<td><p>Checks the provided project for errors that would occur while merging with the current package.</p></td>
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
<td><p><a href="packagewriterdispose-method.md" data-raw-source="[Dispose](packagewriterdispose-method.md)">Dispose</a></p></td>
<td><p>Overloaded.</p></td>
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

 

 

 






