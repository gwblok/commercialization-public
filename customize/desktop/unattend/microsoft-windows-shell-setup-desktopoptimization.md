---
title: DesktopOptimization
description: DesktopOptimization
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cba4a9f6-23eb-413e-a29b-451bb47dfdb7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DesktopOptimization

`DesktopOptimization` specifies display settings that affect the desktop.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [GoToDesktopOnSignIn](microsoft-windows-shell-setup-desktopoptimization-gotodesktoponsignin.md) | Specifies to go to the desktop instead of Start Screen when signing in or when all the apps on a screen are closed. |
| [ShowWindowsStoreAppsOnTaskbar](microsoft-windows-shell-setup-desktopoptimization-showwindowsstoreappsontaskbar.md) | Specifies to show Microsoft Store apps on the taskbar. |

> [!Important]
> It’s recommended that both settings, **GoToDesktopOnSignIn** and **ShowWindowsStoreAppsOnTaskbar**, be set to a consistent value, either both set to **true** or both set to **false**.

## Valid Configuration Passes

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **DesktopOptimization**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output specifies to go to the desktop on sign in and to show Microsoft Store apps on the taskbar.

```XML
<DesktopOptimization>
         <GoToDesktopOnSignIn>true</GoToDesktopOnSignIn>
         <ShowWindowsStoreAppsOnTaskbar>true</ShowWindowsStoreAppsOnTaskbar>
</DesktopOptimization>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
