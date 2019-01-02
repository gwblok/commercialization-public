---
title: HKLMReceiveTimeOut
description: HKLMReceiveTimeOut
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: eb04b5fd-ddc0-48c6-a1a4-2330b7b76fb1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMReceiveTimeOut


`HKLMReceiveTimeOut` specifies the number of milliseconds to wait for data to be received over the network for all users on the computer. This is also known as a socket receive.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number_of_milliseconds</em></p></td>
<td><p>Specifies the number of milliseconds for data to be received over the network before timing out.</p>
<p>The default value is <strong>30000</strong> (30 seconds). <em>Number_of_milliseconds</em> is an integer from 5000 (five seconds) through 86400000 (one day).</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMReceiveTimeOut**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to set Internet Explorer to wait 45 seconds to receive a response to a request. If the response takes longer than this time-out value, the request is canceled.

```
<HKLMReceiveTimeOut>45000</HKLMReceiveTimeOut>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







