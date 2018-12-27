---
title: LockScreen
description: LockScreen
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 24f29420-fd21-445c-8f18-093604211744
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# LockScreen

`LockScreen` specifies the application whose monochrome icon appears on the **Lock** screen.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Badge](microsoft-windows-shell-setup-starttiles-lockscreen-badge.md) | A container that holds the <code>AppId</code> value for the application whose monochrome icon appears on the <strong>Lock</strong> screen. |

## Valid Configuration Passes

specialize

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [StartTiles](microsoft-windows-shell-setup-starttiles.md) | **LockScreen**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to use the `LockScreen` component.

```XML
<LockScreen>
  <Badge>
      <AppId>34567ChannelFabrikam.channel-DEF_012ghijk345!App</AppId>
  </Badge>
</LockScreen>
```

## Related topics

[StartTiles](microsoft-windows-shell-setup-starttiles.md)
