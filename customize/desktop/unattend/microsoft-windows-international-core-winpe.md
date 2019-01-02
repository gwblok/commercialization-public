---
title: Microsoft-Windows-International-Core-WinPE
description: Microsoft-Windows-International-Core-WinPE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 66c0e00c-12fe-4f2d-9be4-0b4a81634602
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-International-Core-WinPE

The Microsoft-Windows-International-Core-WinPE component specifies the default language, locale, and other international settings to use during Windows Setup or Windows Deployment Services installations.

The settings in this component can be applied only in the windowsPE configuration pass. To specify language and locale settings in the oobeSystem and specialize configuration passes, see [Microsoft-Windows-International-Core](microsoft-windows-international-core.md).

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [InputLocale](microsoft-windows-international-core-winpe-inputlocale.md) | Specifies the system input locale and the keyboard layout. |
| [LayeredDriver](microsoft-windows-international-core-winpe-layereddriver.md) | Specifies the keyboard driver to use for Japanese or Korean keyboards. |
| [SetupUILanguage](microsoft-windows-international-core-winpe-setupuilanguage.md) | Specifies the default language to use during Windows Setup or Windows Deployment Services. |
| [SystemLocale](microsoft-windows-international-core-winpe-systemlocale.md) | Specifies the default language for non-Unicode programs. |
| [UILanguage](microsoft-windows-international-core-winpe-uilanguage.md) | Specifies the default system user interface (UI) language. |
| [UILanguageFallback](microsoft-windows-international-core-winpe-uilanguagefallback.md) | Specifies the fallback language if the system default UI language is only partially localized. |
| [UserLocale](microsoft-windows-international-core-winpe-userlocale.md) | Specifies the per-user settings used for formatting dates, times, currency, and numbers. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)
