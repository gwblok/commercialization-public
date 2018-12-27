---
title: Region
description: Region
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0b52cb64-934b-4c3f-b922-2829be5d87d9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Region

`Region` specifies a region that, when selected, shows a set of region-specific apps that appear on the Start and Lock screens.

Each regional layout can be used for multiple regions. For example, you could add a set of apps that are designed for South American business travel that only appear for your users in South America.

Your user’s region can be selected by the user during OOBE, or can be specified with Microsoft-Windows-International-Core\\[UserLocale](microsoft-windows-international-core-userlocale.md).

If the selected region matches a region in Windows-Shell-Setup\\StartMenu\\RegionalOverrides\\RegionalOverride\\Regions\\Region, then Windows displays the set of apps from that regional override. The set of apps is specified by Microsoft-Windows-Shell-Setup\\StartTiles\\RegionalOverrides\\[RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md): WideTiles, SquareTiles, and LockScreen.

If the selected region doesn’t match any of these regions, then Windows displays the set of apps from Microsoft-Windows-Shell-Setup\\[StartTiles](microsoft-windows-shell-setup-starttiles.md): WideTiles, SquareTiles, and LockScreen.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CountryOrRegionID](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region-countryorregionid.md) | Specifies a region code for a region that, when selected, shows a set of region-specific apps that appear on the Start and Lock screens. |
| [Key](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region-key.md) | Specifies a unique value for each region. |

## Valid Configuration Passes


specialize

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | [RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md)| [Regions](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions.md) | **Region**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to configure a set of Apps that apply to only in France and Italy.

```XML
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
<RegionalOverrides>
```

## Related topics

[How to Customize the Start Screen](http://go.microsoft.com/fwlink/?LinkId=254187)

[Regions](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions.md)

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[UserLocale](microsoft-windows-international-core-userlocale.md)
