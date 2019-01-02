---
title: IEnumProfile
description: IEnumProfile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a7f512d4-13dd-44be-881b-2b705deb973a
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# IEnumProfile


Provides a standard COM enumeration method for enumerating a collection of [IProfile](iprofile.md) interfaces.

## Syntax


```
{
  [id(1), helpstring("Next")] HRESULT Next
    ([in] ULONG celt,
    [out, size_is(celt), length_is(*pCeltFetched)] IProfile** prgVar,
    [out] ULONG* pCeltFetched);
  [id(2), helpstring("Skip")] HRESULT Skip
    ([in] ULONG celt);
  [id(3), helpstring("Reset")] HRESULT Reset();
  [id(4), helpstring("Clone")] HRESULT Clone
    ([out] IEnumProfile** ppEnum);
};
```

## Functions


The following table describes the functions that this interface provides.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Method</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="next-ienumprofile.md" data-raw-source="[Next](next-ienumprofile.md)">Next</a></p></td>
<td><p>Returns an array that contains the specified number of elements.</p></td>
</tr>
<tr class="even">
<td><p><a href="skip-ienumprofile.md" data-raw-source="[Skip](skip-ienumprofile.md)">Skip</a></p></td>
<td><p>Indicates the number of elements to skip.</p></td>
</tr>
<tr class="odd">
<td><p><a href="reset-ienumprofile.md" data-raw-source="[Reset](reset-ienumprofile.md)">Reset</a></p></td>
<td><p>Resets the enumeration.</p></td>
</tr>
<tr class="even">
<td><p><a href="clone-ienumprofile.md" data-raw-source="[Clone](clone-ienumprofile.md)">Clone</a></p></td>
<td><p>Creates a clone enumerator.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[Interfaces](interfaces-wprcontrol.md)

 

 







