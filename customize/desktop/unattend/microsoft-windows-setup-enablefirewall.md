---
title: EnableFirewall
description: EnableFirewall
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 76e85dfd-ab42-40ed-b352-0633b133dd4a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableFirewall


`EnableFirewall` specifies whether Windows Firewall is enabled for Windows Preinstallation Environment (Windows PE). This setting does not apply to the Windows Firewall settings of the Windows installation.

Windows Firewall is a stateful-host firewall that discards unsolicited incoming traffic, providing a level of protection for computers against malicious users or programs. A *stateful firewall* is a firewall that keeps track of the state of network connections (such as TCP streams or UDP communication) traveling across it. To provide better protection for computers connected to any kind of network (such as the Internet, a home network, or an organization network), the Windows operating system enables Windows Firewall on all network connections by default.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Enables Windows Firewall for Windows PE. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Disables Windows Firewall for Windows PE.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **EnableFirewall**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output disables the Windows Firewall.

```
<EnableFirewall>false</EnableFirewall>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 







