---
title: Enable
description: Enable
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 93cd37d6-915b-45ea-adf3-5e83bdcf20ac
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Enable


`Enable` specifies whether dynamic updates are enabled for installation.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Enables dynamic updates.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Disables dynamic updates. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [DynamicUpdate](microsoft-windows-setup-dynamicupdate.md) | **Enable**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows the value for the `DynamicUpdate` setting.

```
<DynamicUpdate>
     <Enable>true</Enable>
     <WillShowUI>Never</WillShowUI>
</DynamicUpdate>
```

## Related topics


[DynamicUpdate](microsoft-windows-setup-dynamicupdate.md)

 

 







