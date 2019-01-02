---
title: IFilter Members
description: IFilter Members
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4f282424-4ee8-4ce3-9329-4e752e5f19af


ms.date: 10/15/2017
ms.topic: article


---

# IFilter Members


The following tables list the members exposed by the **IFilter** type.

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
<td><p><a href="ifilterconstraints-property.md" data-raw-source="[IFilter.Constraints Property](ifilterconstraints-property.md)">IFilter.Constraints Property</a></p></td>
<td><p>This property represents the filter constraints for the filter.</p></td>
</tr>
<tr class="even">
<td><p><a href="ifilterexpirationdate-property.md" data-raw-source="[IFilter.ExpirationDate Property](ifilterexpirationdate-property.md)">IFilter.ExpirationDate Property</a></p></td>
<td><p>This property represents the expiration date for the filter.</p></td>
</tr>
<tr class="odd">
<td><p><a href="ifilterfilternumber-property.md" data-raw-source="[IFilter.FilterNumber Property](ifilterfilternumber-property.md)">IFilter.FilterNumber Property</a></p></td>
<td><p>This property represents the filter ID number. The Filter ID number uniquely identifies a filter within the HCK.</p></td>
</tr>
<tr class="even">
<td><p><a href="ifilterfilternumber-property.md" data-raw-source="[IFilter.FilterNumber Property](ifilterfilternumber-property.md)">IFilter.FilterNumber Property</a></p></td>
<td><p>This property determines whether the logs are required for this filter to be applicable.</p></td>
</tr>
<tr class="odd">
<td><p><a href="ifilterisresultrequired-property.md" data-raw-source="[IFilter.IsResultRequired Property](ifilterisresultrequired-property.md)">IFilter.IsResultRequired Property</a></p></td>
<td><p>This property represents determines whether the results are required for this filter to be applicable.</p></td>
</tr>
<tr class="even">
<td><p>IssueDescription</p></td>
<td><p>This property represents the issue description for the filter.</p></td>
</tr>
<tr class="odd">
<td><p>IssueResolution</p></td>
<td><p>This property represents the issue resolution for the filter.</p></td>
</tr>
<tr class="even">
<td><p>LastModifiedDate</p></td>
<td><p>This property represents the last modified date for the filter.</p></td>
</tr>
<tr class="odd">
<td><p>LogNodes</p></td>
<td><p>This property represents the filter log nodes for the filter.</p></td>
</tr>
<tr class="even">
<td><p>ShouldFilterAllZeros</p></td>
<td><p>This property determines whether the filter should be applied if the pass and fail count are both zero.</p></td>
</tr>
<tr class="odd">
<td><p>ShouldFilterNotRuns</p></td>
<td><p>This property determines whether the filter should be applied for not run task results.</p></td>
</tr>
<tr class="even">
<td><p>Status</p></td>
<td><p>This property represents the status for the filter.</p></td>
</tr>
<tr class="odd">
<td><p>TestCommandLine</p></td>
<td><p>This property represents the command line for the test being filtered.</p></td>
</tr>
<tr class="even">
<td><p>Title</p></td>
<td><p>This property represents the filter title value (string).</p></td>
</tr>
<tr class="odd">
<td><p>Type</p></td>
<td><p>This property represents the filter type for the given filter.</p></td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>This property represents the version for the filter.</p></td>
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
<td><p><a href="ifilterisapplicable-method.md" data-raw-source="[IFilter.IsApplicable Method](ifilterisapplicable-method.md)">IFilter.IsApplicable Method</a></p></td>
<td><p>This method determines whether the filter is applicable for the given taskResult.</p></td>
</tr>
</tbody>
</table>

 

 

 






