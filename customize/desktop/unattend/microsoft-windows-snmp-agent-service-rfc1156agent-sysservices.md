---
title: sysServices
description: sysServices
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 77b6f60e-fb08-4c5c-9164-0b19fbf78632
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# sysServices


`sysServices` specifies any combination of up to five Simple Network Management Protocol (SNMP) services.

The integer value is derived from the following binary values:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Service</th>
<th>Binary Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Physical</p></td>
<td><p>0x01</p></td>
</tr>
<tr class="even">
<td><p>DataLink and Subnet</p></td>
<td><p>0x02</p></td>
</tr>
<tr class="odd">
<td><p>Internet</p></td>
<td><p>0x04</p></td>
</tr>
<tr class="even">
<td><p>End-to-end</p></td>
<td><p>0x08</p></td>
</tr>
<tr class="odd">
<td><p>Application</p></td>
<td><p>0x40</p></td>
</tr>
</tbody>
</table>

 

For example, a combination of **Physical** and **Application** has a value of 0x41 (65).

You can use this setting in core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012, by enabling **SNMP-SC** in the Windows Foundation package.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>SysServices</em></p></td>
<td><p>Specifies any combination of up to five SNMP services. <em>SysServices</em> is an integer. The default value is <strong>76</strong>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md) | [RFC1156Agent](microsoft-windows-snmp-agent-service-rfc1156agent.md) | **sysServices**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SNMP-Agent-Service](microsoft-windows-snmp-agent-service.md).

## XML Example


The following XML sample output shows how to set SNMP.

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
      <Traps>207.46.197.32</Traps>
   </TrapConfigurationItems>
</TrapConfiguration>
<ValidCommunities>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community1">2</ValidCommunity>
   <ValidCommunity wcm:action="add" wcm:keyValue="Community2">4</ValidCommunity>
</ValidCommunities>
```

## Related topics


[RFC1156Agent](microsoft-windows-snmp-agent-service-rfc1156agent.md)

 

 







