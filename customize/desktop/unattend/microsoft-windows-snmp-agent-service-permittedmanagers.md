---
title: PermittedManagers
description: PermittedManagers
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 19b926cd-d3ff-417a-956d-3d216f6dd183
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PermittedManagers

`PermittedManagers` specifies whether the computer accepts Simple Network Management Protocol (SNMP) requests from any host.

If a host is specified in [A1](microsoft-windows-snmp-agent-service-permittedmanagers-a1.md), the computer accepts SNMP requests only from that host. You can specify either the host computer name or its IP address for the host. It is recommended that `Host` be used as the host computer name.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [A1](microsoft-windows-snmp-agent-service-permittedmanagers-a1.md) | Specifies a host from which the computer accepts SNMP requests. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | **PermittedManagers**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md).

## XML Example

The following XML output shows how to set SNMP.

```XML
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
      <Traps>207.46.197.32</Traps>
   </TrapConfigurationItems>
</TrapConfiguration>
<ValidCommunities>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community1">2</ValidCommunity>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community2">4</ValidCommunity>
</ValidCommunities>
```

## Related topics

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md)
