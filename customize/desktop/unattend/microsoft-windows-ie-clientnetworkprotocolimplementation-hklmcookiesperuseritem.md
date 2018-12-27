---
title: HKLMCookiesPerUserItem
description: HKLMCookiesPerUserItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ee76fa66-7865-4358-85c7-2e88cc60c268
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMCookiesPerUserItem


`HKLMCookiesPerUserItem` specifies whether Microsoft Internet Explorer cookies are cached individually for each user on a specific computer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that cookies are cached individually for each user. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that cookies are not cached individually for each user. There is only a common cache for all users.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMCookiesPerUserItem**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify that there is a common cache on the computer for Internet Explorer cookies.

```
<HKLMCookiesPerUserItem>false</HKLMCookiesPerUserItem>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

[HKLMContentPerUserItem](microsoft-windows-ie-clientnetworkprotocolimplementation-hklmcontentperuseritem.md)

[HKLMHistoryPerUserItem](microsoft-windows-ie-clientnetworkprotocolimplementation-hklmhistoryperuseritem.md)

 

 







