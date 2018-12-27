---
title: HKLMProxyServer
description: HKLMProxyServer
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d090c3ee-85a2-4b79-94a6-f736ae2513f4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMProxyServer


`HKLMProxyServer` specifies the IP address or the host name of the proxy server on the network for all users on the computer.

**Note**  
`HKLMProxyServer` is effective only if the Group Policy for Microsoft Internet Explorer: "Make proxy settings per-machine (rather than per-user)" is set to **Enabled**. This Group Policy is accessible through the registry key:`HKLMSoftware\Policies\Microsoft\Windows\CurrentVersion\InternetSettings`. When this setting is active, it appears as `ProxySettingsPerUser`, as the type: `ProxySettingsPerUser`, as the type: **REG DWORD**, with the default value set to **0**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>hostname</em> or <em>IP_address</em></p></td>
<td><p>Specifies either a host name or the IP address for the proxy server on the network. Both <em>IP_address</em> and <em>hostname</em> are strings.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMProxyServer**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify the IP address of the proxy server on the network for all users on the computer.

```
<HKLMProxyServer>207.46.197.32</HKLMProxyServer>
```

The following XML output shows how to specify the hostname of the proxy server on the network for all users on the computer.

```
<HKLMProxyServer>proxyserver.fabrikam.com</HKLMProxyServer>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







