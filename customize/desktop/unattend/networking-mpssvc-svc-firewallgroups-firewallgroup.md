---
title: FirewallGroup
description: FirewallGroup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8a7d88a9-354f-4ec9-8f13-919de9297b1c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FirewallGroup

`FirewallGroup` specifies a Windows Firewall group.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Active](networking-mpssvc-svc-firewallgroups-firewallgroup-active.md) | Specifies whether a Windows Firewall group is active. |
| [Group](networking-mpssvc-svc-firewallgroups-firewallgroup-group.md) | Specifies a Windows Firewall group by its ID. |
| [Key](networking-mpssvc-svc-firewallgroups-firewallgroup-key.md) | Specifies a unique name that you can use to identify the Firewall group. |
| [Profile](networking-mpssvc-svc-firewallgroups-firewallgroup-profile.md) | Specifies a Windows Firewall group profile. |

## Parent Hierarchy

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | [FirewallGroups](networking-mpssvc-svc-firewallgroups.md) | **FirewallGroup**

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

[FirewallGroups](networking-mpssvc-svc-firewallgroups.md)
