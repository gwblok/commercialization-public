---
title: WaitForText
description: WaitForText
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d030b3b3-421e-4cc1-9752-d5f69a011fae
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# WaitForText


Waits until the user adds the appropriate text strings and calls SetTextAvailable.

## Syntax


```
HRESULT WaitForText
  ([in] ULONG Milliseconds)
;
```

## Parameters


<a href="" id="milliseconds"></a>*Milliseconds*  
\[in\] Indicates the number of milliseconds for the wait delay.

## Return Value


The following table describes possible return values. Failure return values are implementation-specific.

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
<td><p>Indicates success.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[ITraceMergeTextHandler](itracemergetexthandler.md)

 

 







