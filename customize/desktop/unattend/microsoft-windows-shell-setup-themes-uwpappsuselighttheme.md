---
title: UWPAppsUseLightTheme
description: UWPAppsUseLightTheme
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B4EC2C24-6C05-446D-8440-5E376B78918B


ms.date: 05/02/2017
ms.topic: article


---
# UWPAppsUseLightTheme

`UWPAppsUseLightTheme` specifies whether the dark mode is applied.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the classic Windows color mode is used. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the dark color mode is used.</p></td>
</tr>
</tbody>
</table>

## Valid Configuration Passes

specialize

auditSystem

auditUser

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [Themes](microsoft-windows-shell-setup-themes.md) | **UWPAppsUseLightTheme**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set a customized theme.

```xml
<Themes>
   <ThemeName>Fabrikam Theme</ThemeName>
   <DefaultThemesOff>false</DefaultThemesOff>
   <DesktopBackground>%WINDIR%\OEM\CustomizationFiles\Theme1\fabrikam-wallpaper.jpg</DesktopBackground>
   <BrandIcon>%WINDIR%\OEM\CustomizationFiles\Theme1\fabrikam-logo.png</BrandIcon>
   <WindowColor>Automatic</WindowColor>
   <UWPAppsUseLightTheme>false</UWPAppsUseLightTheme>
</Themes>
```

## Related topics

[Themes](microsoft-windows-shell-setup-themes.md)
