---
title: DuplicatorDescription
description: DuplicatorDescription
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 398d0e0d-4a8f-453d-8a5c-1224a3f86d56
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DuplicatorDescription


`DuplicatorDescription` specifies a description of the duplication tool used, as well as any other information that an OEM or an administrator might store in the registry.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>DuplicatorDescription</em></p></td>
<td><p>Specifies a description of the duplication tool used. <em>DuplicatorDescription</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **DuplicatorDescription**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output specifies the duplication tool.

```
<DuplicatorDescription>MyDescription</DuplicatorDescription>
```

## Related topics


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md)

 

 







