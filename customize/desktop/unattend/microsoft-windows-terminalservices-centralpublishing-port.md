---
title: Port
description: Port
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e6d1ca95-f00a-4ac3-a9f8-416c2f930c29
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Port


`Port` specifies the RPC port for Terminal Services RemoteApp and Remote Desktop Connection management.

For more information about configuring RPC ports, see the MSDN topic: [How to configure RPC to use certain ports and how to help secure those ports by using IPsec](http://go.microsoft.com/fwlink/?LinkId=143405).

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>port_number</em></p></td>
<td><p>Specifies the port that Terminal Services RemoteApp and Remote Desktop Connection Management uses for communication. The default value is 5504.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-CentralPublishing](microsoft-windows-terminalservices-centralpublishing.md) | **Port**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-CentralPublishing](microsoft-windows-terminalservices-centralpublishing.md).

## XML Example


The following XML output specifies that RemoteApp and Desktop Connection Management use port 5510 for communication.

```
<Port>5510</Port>
```

## Related topics


[Microsoft-Windows-TerminalServices-CentralPublishing](microsoft-windows-terminalservices-centralpublishing.md)

 

 







