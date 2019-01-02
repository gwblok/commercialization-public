---
title: IcmpRedirectsEnabled
description: IcmpRedirectsEnabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 16fd84d7-acb8-4064-a052-d0dcc82532ae
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IcmpRedirectsEnabled


`IcmpRedirectsEnabled` specifies whether the IPv4 and IPv6 path caches are updated in response to Internet Control Message Protocol (ICMP) redirect messages.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the IPv4 and IPv6 path caches are updated in response to ICMP redirect messages. This is the default value for both the IPv4 and IPv6 settings.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the IPv4 and IPv6 path caches are not updated in response to ICMP redirect messages.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

windowsPE

## Parent Hierarchy


[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md) | **IcmpRedirectsEnabled**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md).

## XML Example


The following XML output shows how to disable ICMP redirects.

```
<IcmpRedirectsEnabled>false</IcmpRedirectsEnabled>
```

## Related topics


[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md)

 

 







