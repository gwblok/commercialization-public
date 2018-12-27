---
title: HKLMProxyEnable
description: HKLMProxyEnable
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 19f76299-5bcb-4704-b5eb-ce15cd8cb1c6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HKLMProxyEnable


`HKLMProxyEnable` specifies whether to use a proxy server to connect to the Internet for all users on the computer.

**Note**  
`HKLMProxyEnable` is effective only if the Group Policy for Microsoft Internet Explorer: "Make proxy settings per-machine (rather than per-user)" is set to **Enabled**. This Group Policy is accessible through the registry key: `HKLMSoftware\Policies\Microsoft\Windows\CurrentVersion\InternetSettings`. When this setting is active, it appears as `ProxySettingsPerUser`, as the type: **REG DWORD**, with the default value set to **0**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that a proxy server be used to connect to the Internet.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that a proxy server not be used to connect to the Internet. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md) | **HKLMProxyEnable**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md).

## XML Example


The following XML output shows how to specify that a proxy server be used to connect to the Internet.

```
<HKLMProxyEnable>true</HKLMProxyEnable>
```

## Related topics


[microsoft-windows-ie-clientnetworkprotocolimplementation-](microsoft-windows-ie-clientnetworkprotocolimplementation.md)

 

 







