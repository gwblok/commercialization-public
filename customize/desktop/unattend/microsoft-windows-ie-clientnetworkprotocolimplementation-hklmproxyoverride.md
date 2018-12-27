---
title: HKLMProxyOverride
description: HKLMProxyOverride
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4771aacf-07bb-438a-8f3a-2ce9c600b4d7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMProxyOverride


`HKLMProxyOverride` specifies a list of host names or IP addresses that bypasses the proxy server for all users on the computer.

**Note**  
`HKLMProxyOverride` is effective only if the Group Policy for Microsoft Internet Explorer: "Make proxy settings per-machine (rather than per-user)" is set to **Enabled**. This Group Policy is accessible through the registry key: `HKLMSoftware\Policies\Microsoft\Windows\CurrentVersion\InternetSettings`. When this setting is active, it appears as `ProxySettingsPerUser`, as the type: **REG DWORD** with the default value set to **0**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>list_of_hostnames</em> or <em>IP_addresses</em></p></td>
<td><p>Specifies one or more host names or IP addresses that bypass the proxy server. You can add multiple entries by using semicolons as the separator. Both <em>IP_addresses</em> and <em>list_of_hostnames</em> are strings.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

**Note**  
If you require more than one address, list multiple addresses separated by semicolons. Include the string `<local>` to bypass the proxy server for all intranet addresses.

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMProxyOverride**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify a list of host names or IP addresses that bypass the proxy server for all users on the computer.

```
<HKLMProxyEnable>true</HKLMProxyEnable>
<HKLMProxyOverride>www.fabrikam.com;*.contoso.com; 207.46.197.32</HKLMProxyOverride>
<HKLMProxyServer>207.46.197.32</HKLMProxyServer>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







