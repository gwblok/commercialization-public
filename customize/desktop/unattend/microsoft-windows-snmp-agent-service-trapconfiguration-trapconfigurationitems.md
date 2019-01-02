---
title: TrapConfigurationItems
description: TrapConfigurationItems
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6ea4d3c1-c86b-4a7c-8162-10bc2cdb9111
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# TrapConfigurationItems

`TrapConfigurationItems` specifies details about the community name and traps used by the trap configuration.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Community_Name](microsoft-windows-snmp-agent-service-trapconfiguration-trapconfigurationitems-community-name.md) | Specifies the name of the community to which Simple Network Management Protocol (SNMP) sends traps. |
| [Traps](microsoft-windows-snmp-agent-service-trapconfiguration-trapconfigurationitems-traps.md) | Specifies the IP addresses to which SNMP sends traps. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | [TrapConfiguration](microsoft-windows-snmp-agent-service-trapconfiguration.md) | **TrapConfigurationItems**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md).

## XML Example

The following XML sample output shows how to set SNMP.

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

[TrapConfiguration](microsoft-windows-snmp-agent-service-trapconfiguration.md)
