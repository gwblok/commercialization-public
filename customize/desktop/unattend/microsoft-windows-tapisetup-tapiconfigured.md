---
title: TapiConfigured
description: TapiConfigured
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 162b218b-d65c-4009-bbc9-926e1e582a71
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TapiConfigured


`TapiConfigured` specifies whether to retain or to rewrite the telephony locations.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies to rewrite the configured telephony locations.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies to retain the configured telephony locations. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md) | **TapiConfigured**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md).

## XML Example


The following XML output shows how to rewrite the configured telephony locations.

```
<TapiConfigured>0</TapiConfigured>
```

## Related topics


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md)

 

 







