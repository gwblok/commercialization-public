---
title: HKLMContentPerUserItem
description: HKLMContentPerUserItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 35c57eb9-5c18-44d9-851e-e298364d2c57
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMContentPerUserItem


`HKLMContentPerUserItem` specifies whether Microsoft Internet Explorer content is cached individually for each user.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that content is cached individually for each user. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that content is not cached individually for each user. There is only a common cache for all users.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMContentPerUserItem**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify that there is a common cache for all users for Internet Explorer content.

```
<HKLMContentPerUserItem>false</HKLMContentPerUserItem>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

[HKLMCookiesPerUserItem](microsoft-windows-ie-clientnetworkprotocolimplementation-hklmcookiesperuseritem.md)

[HKLMHistoryPerUserItem](microsoft-windows-ie-clientnetworkprotocolimplementation-hklmhistoryperuseritem.md)

 

 







