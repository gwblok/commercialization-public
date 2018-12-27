---
title: Order
description: Order
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1083cdcf-8fa4-4d1a-8ee4-fe691ac5f3ac
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Order


`Order` specifies a unique id for a set of regions. In the specified set of regions, Windows displays a customized set of apps that appear on the Start and Lock screens.

Each regional override can be used for multiple regions. For example, you could add a set of apps that are designed for South American business travel that only appear for your users in South America.

Your user’s region can be selected by the user during OOBE, or can be specified with Microsoft-Windows-International-Core\\[UserLocale](microsoft-windows-international-core-userlocale.md).

If the selected region matches a region in Windows-Shell-Setup\\StartMenu\\RegionalOverrides\\RegionalOverride\\Regions\\[Region](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region.md), then Windows displays the set of apps from that regional override. The set of apps is specified by Microsoft-Windows-Shell-Setup\\StartTiles\\RegionalOverrides\\[RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md): WideTiles, SquareTiles, and LockScreen.

If the selected region doesn’t match any of these regions, then Windows displays the set of apps from Microsoft-Windows-Shell-Setup\\[StartTiles](microsoft-windows-shell-setup-starttiles.md): WideTiles, SquareTiles, and LockScreen.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Order</em></p></td>
<td><p>Specifies a unique ID for the regional override.</p>
<p>This value must be a three-digit integer between 001 and 199: 001, 002, 003, 004, 005, 006, 007, 008, 009, 010 … 199.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | [RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md)| **Order**

## XML Example


The following XML output shows how to configure two set of apps, one applies to only in France and Italy, another applies only to Germany.

```
<RegionalOverrides>
  <RegionalOverride>
    <Order>1</Order>
    <Regions>
      <Region>
        <RegionID>IT</RegionID>
      </Region>
      <Region>
        <RegionID>FR</RegionID>
      </Region>
     </Regions>
    <!-- Square tiles, Wide Tiles, and LockScreen apps are specified here -->
  </RegionalOverride>
  <RegionalOverride>
    <Order>2</Order>
    <Regions>
      <Region>
        <RegionID>DE</RegionID>
      </Region>
     </Regions>
    <!-- Square tiles, Wide Tiles, and LockScreen apps are specified here -->
  </RegionalOverride>
<Regions>
```

## Related topics


[How to Customize the Start Screen](http://go.microsoft.com/fwlink/?LinkId=254187)

[Region](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region.md)

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[UserLocale](microsoft-windows-international-core-userlocale.md)

 

 







