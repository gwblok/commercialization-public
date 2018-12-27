---
title: FirewallGroups
description: FirewallGroups
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 359cb5d9-7711-4f40-a22f-62eb99ee70ce
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FirewallGroups

`FirewallGroups` specifies Windows Firewall groups.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md) | Specifies a Windows Firewall group. |

## Parent Hierarchy

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | **FirewallGroups**

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

> [!Note]
> The `Group` value must be the Group ID associated with the firewall group you want to reference (for example, the `Remote Desktop` group corresponds to the ID `@FirewallAPI.dll,-28752`). Group IDs can be obtained using Network Security commands in PowerShell. See the child topic on the [Group](networking-mpssvc-svc-firewallgroups-firewallgroup-group.md) parameter for more detailed instructions.

## Related topics

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md)
