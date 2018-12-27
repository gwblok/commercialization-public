---
title: Badge
description: Badge
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a38102e2-6442-4ae6-9000-b0872437f149
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Badge

`Badge` is a container that holds the `AppId` value for the application whose monochrome icon appears on the **Lock** screen. No additional work is required on your end to make it monochrome; Windows does that automatically. Lock screen badges should only show toast notifications, be easy to understand, include only personally relevant information, and should stay current so users can scan the tile to get the latest information. Clicking on the badge does not activate the app.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AppId](microsoft-windows-shell-setup-starttiles-lockscreen-badge-appid.md) | Specifies the application whose monochrome icon appears on the <strong>Lock</strong> screen. |

## Valid Configuration Passes

specialize

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [StartTiles](microsoft-windows-shell-setup-starttiles.md) | [LockScreen](microsoft-windows-shell-setup-starttiles-lockscreen.md) | **Badge**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set [LockScreen](microsoft-windows-shell-setup-starttiles-lockscreen.md).

```XML
<LockScreen>
  <Badge>
      <AppId>34567ChannelFabrikam.channel-DEF_012ghijk345!App</AppId>
  </Badge>
</LockScreen>
```

## Related topics

[SquareTiles](microsoft-windows-shell-setup-starttiles-squaretiles.md)

[WideTiles](microsoft-windows-shell-setup-starttiles-widetiles.md)
