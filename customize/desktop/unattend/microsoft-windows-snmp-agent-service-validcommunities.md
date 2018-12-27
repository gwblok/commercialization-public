---
title: ValidCommunities
description: ValidCommunities
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 39f79faf-8b3d-42da-a734-fabec5797434
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ValidCommunities

`ValidCommunities` is a container for [ValidCommunity](microsoft-windows-snmp-agent-service-validcommunities-validcommunity.md) elements.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ValidCommunity](microsoft-windows-snmp-agent-service-validcommunities-validcommunity.md) | Specifies the community name from which the computer running Simple Network Management Protocol (SNMP) can accept SNMP requests, such as GET, SET, GETNEXT, and GETBULK. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | **ValidCommunities**

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

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md)
