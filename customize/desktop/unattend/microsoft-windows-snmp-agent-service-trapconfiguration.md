---
title: TrapConfiguration
description: TrapConfiguration
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2bf28805-7283-4919-9e78-5fb49cff22d7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# TrapConfiguration

`TrapConfiguration` specifies settings for trap configuration items.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [TrapConfigurationItems](microsoft-windows-snmp-agent-service-trapconfiguration-trapconfigurationitems.md) | Specifies details about individual trap configuration items. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | **TrapConfiguration**

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
