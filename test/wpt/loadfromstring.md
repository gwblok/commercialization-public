---
title: LoadFromString
description: LoadFromString
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c4661c55-e237-4143-af70-dff6de0afe9b
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# LoadFromString


Loads a profile from the specified XML profile definition string.

## Syntax


```
HRESULT LoadFromString
  ([in] BSTR bstrProfile)
;
```

## Parameters


<a href="" id="bstrprofile"></a>*bstrProfile*  
\[in\] A string that contains the XML profile definition.

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
<td><p>The function successfully loaded the profile.</p></td>
</tr>
<tr class="even">
<td><p>E_INVALIDARG</p></td>
<td><p>One or more arguments are invalid. Use <a href="iparsingerrorinfo.md" data-raw-source="[IParsingErrorInfo](iparsingerrorinfo.md)">IParsingErrorInfo</a> to obtain detailed error information.</p></td>
</tr>
<tr class="odd">
<td><p>E_WPRC_FAILED_TO_VALIDATE_PROFILE</p></td>
<td><p>The library failed to validate the profile. Use <strong>IParsingErrorInfo</strong> to obtain detailed error information.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[IProfile](iprofile.md)

 

 







