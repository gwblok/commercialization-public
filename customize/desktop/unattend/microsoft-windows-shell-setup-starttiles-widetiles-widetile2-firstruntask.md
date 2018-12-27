---
title: FirstRunTask
description: FirstRunTask
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9f5f17a1-82ef-40a7-9b32-01143e01007e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FirstRunTask


The `FirstRunTask` setting specifies the background task that is active, or live, by default for a tile when a user signs in to Windows for the first time.

The background task must register the user with Windows Notification Service at first sign-in, and must send notifications to the app’s live tile.

## Values


To make a tile live, do one of the following:

-   If your background task is in JavaScript, specify the .js file that implements the IBackgroundTask interface.

-   If your background task is in XAML or C++, specify the class ID for the application.

## Valid Configuration Passes


specialize

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [WideTiles](microsoft-windows-shell-setup-starttiles-widetiles.md) | [WideTile2](microsoft-windows-shell-setup-starttiles-widetiles-widetile2.md) | **FirstRunTask**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to use the `<WideTiles>` component.

```
     <WideTiles>
          <WideTile1>
               <AppId>12345ChannelFabrikam.channel-ABC_defghij6789!App</AppId>
               <FirstRunTask>backgroundtask.js</FirstRunTask>
          </WideTile1>
          <WideTile2>
               <AppId>34567ChannelFabrikam.channel-DEF_012ghijk345!App</AppId>
               <FirstRunTask>Fabrikam.FirstRunTask</FirstRunTask>
          </WideTile2>
          <WideTile3>
               <AppId>56789ChannelFabrikam.channel-GHI_67890jklmno!App</AppId>
          </WideTile3>
     </WideTiles>
```

## Related topics


[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md)

[WideTiles](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-widetiles.md)

[WideTiles](microsoft-windows-shell-setup-starttiles-widetiles.md)

 

 







