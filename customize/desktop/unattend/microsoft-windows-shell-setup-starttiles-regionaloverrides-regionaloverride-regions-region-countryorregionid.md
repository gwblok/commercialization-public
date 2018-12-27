---
title: CountryOrRegionID
description: CountryOrRegionID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8db03f6a-0c71-4ae4-9b27-870207890216
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CountryOrRegionID


`CountryOrRegionID` specifies the region code for a region that, when selected, shows a set of region-specific apps that appear on the Start and Lock screens.

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
<td><p><em>CountryOrRegionID</em></p></td>
<td><p>Specifies the two-letter country or region ID of the end user (for example, US, FR, ES).</p>
<p>For the list of valid values for <em>CountryOrRegionID</em>, see <a href="http://go.microsoft.com/fwlink/?LinkId=255198" data-raw-source="[http://go.microsoft.com/fwlink/?LinkId=255198](http://go.microsoft.com/fwlink/?LinkId=255198)">http://go.microsoft.com/fwlink/?LinkId=255198</a>.</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | [RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md)| [Regions](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions.md) | [Region](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region.md) | **CountryOrRegionID**

## XML Example


The following XML output shows how to configure a set of Apps that apply to only in France and Italy.

```
<RegionalOverrides>
  <RegionalOverride>
    <Order>1</Order>
    <Regions>
      <Region>
        <CountryOrRegionID>IT</CountryOrRegionID>
        <Key>1</Key>
      </Region>
      <Region>
        <CountryOrRegionID>FR</CountryOrRegionID>
        <Key>2</Key>
      </Region>
     </Regions>
    <!-- Square tiles, Wide Tiles, and LockScreen apps are specified here -->
  </RegionalOverride>
</RegionalOverrides>
```

## Related topics


[How to Customize the Start Screen](http://go.microsoft.com/fwlink/?LinkId=254187)

[Region](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region.md)

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[UserLocale](microsoft-windows-international-core-userlocale.md)

 

 







