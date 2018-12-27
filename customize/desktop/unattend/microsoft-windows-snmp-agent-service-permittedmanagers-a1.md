---
title: A1
description: A1
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2e02554a-f2cd-47b7-b62a-8fa9a97e290c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# A1


`A1` specifies whether the computer accepts Simple Network Management Protocol (SNMP) requests from any host.

If a host is specified in `A1`, the computer accepts SNMP requests only from that host. You can specify either the host computer name or the IP address for the host. It is recommended that `Host` be used as the host computer name.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>A1</em></p></td>
<td><p>Specifies the host from which the computer accepts SNMP packets. <em>A1</em> is a string.</p>
<p>The default value is <strong>localhost</strong>, which specifies that the computer accepts SNMP requests from any host.</p>
<div class="alert">
<strong>Note</strong><br/><p>The <code>A1</code> setting accepts either <strong>localhost</strong> or a single host. Adding multiple hosts is not supported.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | [PermittedManagers](microsoft-windows-snmp-agent-service-permittedmanagers.md) | **A1**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md).

## XML Example


The following XML output shows how to set SNMP.

```
<PermittedManagers>
   <A1>networkhost</A1>
</PermittedManagers>
<RFC1156Agent>
   <sysContact>MyContact</sysContact>
   <sysLocation>MyLocation</sysLocation>
   <sysServices>65</sysServices>
</RFC1156Agent>
<TrapConfiguration>
   <TrapConfigurationItems wcm:action="add">
      <Community_Name>Private</Community_Name>
      <Traps>ComputerName</Traps>
   </TrapConfigurationItems>
   <TrapConfigurationItems wcm:action="add">
      <Community_Name>Public</Community_Name>
      <Traps>123.45.67.89</Traps>
   </TrapConfigurationItems>
</TrapConfiguration>
<ValidCommunities>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community1">2</ValidCommunity>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community2">4</ValidCommunity>
</ValidCommunities>
```

## Related topics


[PermittedManagers](microsoft-windows-snmp-agent-service-permittedmanagers.md)











