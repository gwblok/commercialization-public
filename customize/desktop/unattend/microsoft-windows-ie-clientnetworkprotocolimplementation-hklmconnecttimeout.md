---
title: HKLMConnectTimeOut
description: HKLMConnectTimeOut
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 72644a17-ad1e-4b8a-9285-537a0fd0696f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMConnectTimeOut


`HKLMConnectTimeOut` specifies the number of milliseconds to wait for an Internet connection request to complete for all users. After this timeout limit is reached, the request is canceled.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number_of_milliseconds</em></p></td>
<td><p>Specifies the number of milliseconds to wait before timing out. The default value is <strong>60000</strong> (one minute). <em>Number_of_milliseconds</em> is an integer from 5000 (five seconds) through 86400000 (one day).</p>
<p>Setting this option to <strong>0</strong> will disable this timer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMConnectTimeOut**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to set the timeout limit to two minutes.

```
<HKLMConnectRetries>1</HKLMConnectRetries>
<HKLMConnectTimeOut>120000</HKLMConnectTimeOut>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







