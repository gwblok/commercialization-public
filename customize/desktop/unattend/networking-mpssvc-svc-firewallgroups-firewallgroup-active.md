---
title: Active
description: Active
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 85a69bf4-888b-4222-b1e1-a88845454617
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Active

`Active` specifies whether a [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md) is active.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that a Windows Firewall group is active.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that a Windows Firewall group is not active. This is the default value.</p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | [FirewallGroups](networking-mpssvc-svc-firewallgroups.md) | [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md) | **Active**

## Valid Configuration Passes

specialize

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Networking-MPSSVC-Svc](networking-mpssvc-svc.md).

## XML Example

The following XML output shows how to set Windows Firewall groups.

```XML
<FirewallGroups>
      <FirewallGroup wcm:action="add" wcm:keyValue="RemoteDesktop">
      <Active>true</Active>
      <Group>@FirewallAPI.dll,-28752</Group>
      <Profile>all</Profile>
   </FirewallGroup>
</FirewallGroups>
```

## Related topics

[FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md)
