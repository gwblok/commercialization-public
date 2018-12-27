---
title: HKLMSendTimeOut
description: HKLMSendTimeOut
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6831f7d6-d44d-42c7-9548-6d7f236dc520
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMSendTimeOut


`HKLMSendTimeOut` specifies the number of milliseconds to wait for data to be sent over the network for all users. This is also known as a socket send.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number_of_milliseconds</em></p></td>
<td><p>Specifies the number of milliseconds to wait for a socket send to complete. The default value is <strong>30000</strong> (30 seconds). <em>Number_of_milliseconds</em> is an integer from 5000 (five seconds) through 86400000 (one day).</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMSendTimeOut**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify that the system waits two minutes for data to be sent over the network. If the send takes longer than this time-out value, the send is canceled..

```
 
<HKLMConnectTimeOut>120000</HKLMConnectTimeOut>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







