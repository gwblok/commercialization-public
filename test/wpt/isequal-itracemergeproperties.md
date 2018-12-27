---
title: IsEqual
description: IsEqual
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ad2c2023-6748-4fc3-b2c4-02bf92637dc0
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# IsEqual


Compares two [ITraceMergeProperties](itracemergeproperties.md) objects.

## Syntax


```
HRESULT IsEqual
  ([in] ITraceMergeProperties* pTraceMergeProperties)
;
```

## Parameters


<a href="" id="ptracemergeproperties"></a>*pTraceMergeProperties*  
\[in\] A pointer to an **ITraceMergeProperties** object to be compared.

## Return Value


The following table describes possible return values.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Return Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>S_OK</p></td>
<td><p>The objects have same trace merge properties.</p></td>
</tr>
<tr class="even">
<td><p>S_FALSE</p></td>
<td><p>The objects do not have the same trace merge properties.</p></td>
</tr>
<tr class="odd">
<td><p>E_INVALIDARG</p></td>
<td><p>One or more arguments are invalid. Use <a href="iparsingerrorinfo.md" data-raw-source="[IParsingErrorInfo](iparsingerrorinfo.md)">IParsingErrorInfo</a> to obtain detailed error information.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[ITraceMergeProperties](itracemergeproperties.md)

 

 







