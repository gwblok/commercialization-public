---
title: RouterType
description: RouterType
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1a5c7538-c559-4825-b697-832e5feb251b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# RouterType


`RouterType` specifies the router type for Remote Access Service (RAS).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that RAS is supported. This is the value for dial-up access.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Specifies that a local area network (LAN) is supported. This is the value for network address translation (NAT) access.</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Specifies that RAS and LAN are both supported.</p></td>
</tr>
<tr class="even">
<td><p><strong>4</strong></p></td>
<td><p>Specifies that a wide area network (WAN) for on-demand dialing is supported. This is the value for demand-dial routing.</p></td>
</tr>
<tr class="odd">
<td><p><strong>5</strong></p></td>
<td><p>Specifies that RAS and WAN are supported.</p></td>
</tr>
<tr class="even">
<td><p><strong>6</strong></p></td>
<td><p>Specifies that LAN and WAN are supported.</p></td>
</tr>
<tr class="odd">
<td><p><strong>7</strong></p></td>
<td><p>Specifies that RAS, LAN, and WAN are all supported. This is the value for virtual private network (VPN) access.</p></td>
</tr>
</tbody>
</table>

 

The default value is **7**.

## Parent Hierarchy


[Microsoft-Windows-RasServer](microsoft-windows-rasserver.md) | **RouterType**

## Valid Configuration Passes


specialize

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-RasServer](microsoft-windows-rasserver.md).

## XML Example


The following XML output shows how to enable RAS and set the router type for LAN access.

```
<ConfigurationFlags>true</ConfigurationFlags> 
<RouterType>2</RouterType>
```

## Related topics


[Microsoft-Windows-RasServer](microsoft-windows-rasserver.md)

 

 







