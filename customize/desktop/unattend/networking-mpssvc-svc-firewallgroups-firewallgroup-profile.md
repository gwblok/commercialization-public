---
title: Profile
description: Profile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b349b4b8-6fa1-45fa-b7d8-ccba0abfc404
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Profile

`Profile` specifies the profile of a [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md).

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>all</strong></p></td>
<td><p>Specifies all profiles.</p></td>
</tr>
<tr class="even">
<td><p><strong>domain</strong></p></td>
<td><p>Specifies the domain profile. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>private</strong></p></td>
<td><p>Specifies the private profile.</p></td>
</tr>
<tr class="even">
<td><p><strong>public</strong></p></td>
<td><p>Specifies the public profile.</p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | [FirewallGroups](networking-mpssvc-svc-firewallgroups.md) | [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md) | **Profile**

## Valid Configuration Passes

specialize

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Networking-MPSSVC-Svc](networking-mpssvc-svc.md).

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
