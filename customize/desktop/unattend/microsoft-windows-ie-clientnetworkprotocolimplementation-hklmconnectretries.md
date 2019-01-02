---
title: HKLMConnectRetries
description: HKLMConnectRetries
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b77b168b-0c25-4271-ac7d-db800e530854
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMConnectRetries


`HKLMConnectRetries` specifies the number of times that the system attempts to resolve and connect to a host before the request is canceled.

The system makes only one attempt per IP address.

If a host has only one IP address and the first connection attempt fails, there are no further attempts. If a connection attempt still fails after the specified number of attempts, the request is canceled.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number_of_retries</em></p></td>
<td><p>Specifies the number of times the system attempts to resolve and connect to a host before the request is canceled.</p>
<p>The default value is <strong>5</strong>. <em>Number_of_retries</em> is an integer between 1 and 100.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMConnectRetries**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Examples


The following XML example shows how to specify that the system try the first two IP addresses in the list. If the host has seven IP addresses, the system tries only the first two IP addresses because `HKLMConnectRetries` is set to **2**.

```
<HKLMConnectRetries>2</HKLMConnectRetries>
```

The following XML example shows how to specify that the system try 10 IP addresses. If the host has seven IP addresses, the system tries seven times, because the system attempts each IP address only once.

```
<HKLMConnectRetries>10</HKLMConnectRetries>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







