---
title: SquareTiles
description: SquareTiles
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9f9649a7-1456-4eae-be44-dbeb769e4245
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# SquareTiles

`SquareTiles` defines the default Microsoft Store apps to appear as square tiles on the **Start** screen.

If the region of the current user account is among those in the Start Tile regional overrides, you can use this setting. For more information, see [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md).

The two available `SquareTiles` types are:

* `DesktopOrSquareTile`. You can include up to 6 of these on your **Start** screen, formatted as `DesktopOrSquareTile1` through `DesktopOrSquareTile6`.
* `SquareTile`. You can include up to 12 of these on your **Start** screen, formatted as `SquareTile1` through `SquareTile12`.

To use either of these tile types with your Microsoft Store apps, you must include the `AppId`. The `AppId` is the `AppUserModelID` found in the application's AUMIDs.txt file, which is located in the app package downloaded from the OEM channel partner portal of the Microsoft Store. You can also include a `FirstRunTask` setting to specify the background task that should be active, or live, by default for the tile.

If you skip a setting, Windows will rearrange the flow of your app tiles around the position of that setting on the **Start** screen. The flow rearrangement is based on columns and is designed to eliminate gaps. The positions may vary based on the screen size, resolution, and DPI of the PC. For more information about these settings, see the associated [StartTiles](microsoft-windows-shell-setup-starttiles.md) settings topics.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[SquareOrDesktopTile1](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile1.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile1.|
|[SquareOrDesktopTile2](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile2.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile2.|
|[SquareOrDesktopTile3](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile3.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile3.|
|[SquareOrDesktopTile4](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile4.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile4.|
|[SquareOrDesktopTile5](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile5.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile5.|
|[SquareOrDesktopTile6](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile6.md)|Specifies the application that appears on the Start screen, in position SquareOrDesktopTile6.|
|[SquareTile1](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile1.md)|Specifies the application that appears on the Start screen, in position SquareTile1.|
|[SquareTile2](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile2.md)|Specifies the application that appears on the Start screen, in position SquareTile2.|
|[SquareTile3](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile3.md)|Specifies the application that appears on the Start screen, in position SquareTile3.|
|[SquareTile4](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile4.md)|Specifies the application that appears on the Start screen, in position SquareTile4.|
|[SquareTile5](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile5.md)|Specifies the application that appears on the Start screen, in position SquareTile5.|
|[SquareTile6](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile6.md)|Specifies the application that appears on the Start screen, in position SquareTile6.|
|[SquareTile7](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile7.md)|Specifies the application that appears on the Start screen, in position SquareTile7.|
|[SquareTile8](microsoft-windows-shell-setup-starttiles-squaretiles-squaretile8.md)|Specifies the application that appears on the Start screen, in position SquareTile8.|
|[SquareTile9](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile9.md)|Specifies the application that appears on the Start screen, in position SquareTile9.|
|[SquareTile10](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile10.md)|Specifies the application that appears on the Start screen, in position SquareTile10.|
|[SquareTile11](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile11.md)|Specifies the application that appears on the Start screen, in position SquareTile11.|
|[SquareTile12](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile12.md)|Specifies the application that appears on the Start screen, in position SquareTile12.|

## Valid Configuration Passes

specialize

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | | [RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md) | [RegionalOverride](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride.md) | **SquareTiles**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to use the `<SquareTiles>` component and its settings.

```XML
<SquareTiles>
          <SquareOrDesktopTile1>
               <AppIdOrPath>C:\programdata\microsoft\windows\start menu\programs\desktoptile1.lnk</AppIdOrPath>
               <FirstRunTask>backgroundtask.js</FirstRunTask>
          </SquareOrDesktopTile1>
          <SquareOrDesktopTile2>
               <AppIdOrPath>67890ChannelFabrikam.channel-JKL_mnop1234789!App</AppIdOrPath>
               <FirstRunTask>Fabrikam.FirstRunTask</FirstRunTask>
          </SquareOrDesktopTile2>
          <SquareOrDesktopTile3>
               <AppIdOrPath>C:\programdata\microsoft\windows\start menu\programs\desktoptile3.lnk</AppIdOrPath>
          </SquareOrDesktopTile3>
          <SquareTile1>
               <AppId>12345ChannelFabrikam.channel-ABC_defghij6789!App</AppId>
               <FirstRunTask>backgroundtask.js</FirstRunTask>
          </SquareTile1>
          <SquareTile2>
               <AppId>34567ChannelFabrikam.channel-DEF_012ghijk345!App</AppId>
               <FirstRunTask>Fabrikam.FirstRunTask</FirstRunTask>
          </SquareTile2>
          <SquareTile3>
               <AppId>56789ChannelFabrikam.channel-GHI_67890jklmno!App</AppId>
          </SquareTile3>
     </SquareTiles> 
```

## Related topics

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md)

[LockScreen](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-lockscreen.md)
