---
title: ValidCommunity
description: ValidCommunity
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 590f6c68-4a5a-4feb-9dc0-c0bd5270dfe4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ValidCommunity

`ValidCommunity` specifies the community name from which the computer running Simple Network Management Protocol (SNMP) can accept SNMP requests such as GET, SET, GETNEXT, and GETBULK.

> [!Note]
> The child elements do not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add this element to the answer file.

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-snmp-agent-service-validcommunities-validcommunity-key.md) | Specifies a unique key for the community. |
| [Value](microsoft-windows-snmp-agent-service-validcommunities-validcommunity-value.md) | Specifies the type of permissions that the agent has. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | [ValidCommunities](microsoft-windows-snmp-agent-service-validcommunities.md) | **ValidCommunity**

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

[ValidCommunities](microsoft-windows-snmp-agent-service-validcommunities.md)
