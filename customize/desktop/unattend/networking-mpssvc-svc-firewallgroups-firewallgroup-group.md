---
title: Group
description: Group
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 63eb28d1-3b5f-467e-bd34-a679a6e9aa83
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Group

The `Group` setting specifies the name of a [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md). The available rule groups differ by Windows edition.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>GroupID</em></p></td>
<td><p>Specifies the resource ID of a Windows Firewall rule group. <em>GroupID</em> is a string. The default value is an empty string.</p></td>
</tr>
</tbody>
</table>

**To obtain a GroupID**

1. Open PowerShell.
1. Maximize the PowerShell window so it encompasses the full screen (if the window is not maximized, it will not show both columns of information).
1. Enter the following command, which shows all unique groups on the computer which can have firewall rules associated with them:

   ```PowerShell
   Get-NetFirewallRule | sort -unique Group | sort DisplayGroup | ft DisplayGroup, Group
   ```

1. PowerShell will show 2 columns of information. The left column shows the `DisplayGroup`, or the "friendly" name of the group. The right column shows the `Group` associated with the `DisplayGroup`. `Group` may have the same value as `DisplayGroup`, or it may be a string containing a resource ID.
1. Use the value in the right column, `Group`, as the GroupID in your Unattend file.

For more information on the `Get-NetFirewallRule` command, see [Net Security](https://docs.microsoft.com/en-us/powershell/module/netsecurity/?view=win10-ps) in the Windows PowerShell Reference.

## Parent Hierarchy

[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | [FirewallGroups](networking-mpssvc-svc-firewallgroups.md) | [FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md) | **Group**

## Valid Configuration Passes

specialize

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Networking-MPSSVC-Svc](networking-mpssvc-svc.md).

## XML Example

The following XML output shows how to set two Windows Firewall groups, the first for `File and Printer Sharing`, and the second for `Remote Desktop`.

```XML
<FirewallGroups>
      <FirewallGroup wcm:action="add" wcm:keyValue="FileAndPrinterSharing">
      <Active>true</Active>
      <Group>@FirewallAPI.dll,-28502</Group>
      <Profile>all</Profile>
   </FirewallGroup>
      <FirewallGroup wcm:action="add" wcm:keyValue="RemoteDesktop">
      <Active>true</Active>
      <Group>@FirewallAPI.dll,-28752</Group>
      <Profile>all</Profile>
   </FirewallGroup>
</FirewallGroups>
```

## Related topics

[FirewallGroup](networking-mpssvc-svc-firewallgroups-firewallgroup.md)
