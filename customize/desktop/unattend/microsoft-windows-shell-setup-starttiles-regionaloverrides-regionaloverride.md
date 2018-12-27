---
title: RegionalOverride
description: RegionalOverride
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f53910f1-4ce0-4780-a1b9-7b7a48132045
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RegionalOverride

A `RegionalOverride` specifies a set of apps that appear on the Start and Lock screens for different regions.

Each regional override can be used for multiple regions. For example, you could add a set of apps that are designed for South American business travel that only appear for your users in South America.

Your user’s region can be selected by the user during OOBE, or can be specified with Microsoft-Windows-International-Core\\[UserLocale](microsoft-windows-international-core-userlocale.md).

If the selected region matches a region in Windows-Shell-Setup\\StartMenu\\RegionalOverrides\\RegionalOverride\\Regions\\[Region](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions-region.md), then Windows displays the set of apps from that regional override. The set of apps is specified by Microsoft-Windows-Shell-Setup\\StartTiles\\RegionalOverrides\\RegionalOverride: WideTiles, SquareTiles, and LockScreen.

If the selected region doesn’t match any of these regions, then Windows displays the set of apps from Microsoft-Windows-Shell-Setup\\[StartTiles](microsoft-windows-shell-setup-starttiles.md): WideTiles, SquareTiles, and LockScreen.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Order](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-order.md) | Specifies a unique id for a set of regions. In the specified set of regions, Windows displays a customized set of apps that appear on the Start and Lock screens. |
| [LockScreen](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-lockscreen.md) | Specifies application whose monochrome icon appears on the <strong>Lock</strong> screen. |
| [Regions](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-regions.md) | Specifies a set of regions where Windows displays a customized set of apps that appear on the Start and Lock screens. |
| [SquareTiles](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles.md) | Specifies the default Windows Runtime-based apps to appear as square tiles on the Start screen. |
| [WideTiles](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-widetiles.md) | Specifies the default Windows Runtime-based apps to appear as wide tiles on the Start screen. |

## Valid Configuration Passes

specialize

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | **RegionalOverride**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## Related topics

[Customize the Start layout](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/customize-start-layout)

[RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md)

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[UserLocale](microsoft-windows-international-core-userlocale.md)
