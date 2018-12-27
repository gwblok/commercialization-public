---

Description: Learn how to localize a Windows installation
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Localize

ms.date: 11/13/2018
ms.topic: article
ms.custom: RS5
---

# Localize

Set up Windows 10 or Windows Server with the right set of languages, settings, and keyboards or other input devices for customers in different regions.

## Localizing Windows

You can add languages and regional support to Windows 10 (except for Windows 10 Home Single Language and Windows 10 Home Country Specific editions), and Windows Server.

**[Add languages to Windows images](add-language-packs-to-windows.md)**

Windows installations start with at least one language pack and its language components. You can add: 
* [Language packs](available-language-packs-for-windows.md): Fully-localized Windows UI text for the dialog boxes, menu items, and help files that you see in Windows. Delivered as .cab files, for example, Microsoft-Windows-Client-Language-Pack_x64_es-es.cab.
* [Language Interface Packs (LIP)](available-language-packs-for-windows.md#lips): Partially-localized languages. LIPs require a base language pack. For UI that's not localized in the LIP, Windows shows UI from the base language pack. Delivered as .appx files, for example, LanguageExperiencePack.am-et.neutral.appx.
* [Features On Demand](features-on-demand-language-fod.md): Features include language basics (like spell checking), fonts, optical character recognition, handwriting, text-to-speech, and speech recognition. You can save disk space by choosing not to include some language components in your image. While this reduction in image size can be helpful when creating images for lower-cost devices with small storage, it does lead to an incomplete language experience.  Delivered as .cab files, for example, Microsoft-Windows-LanguageFeatures-Basic-fr-fr-Package.
* [Recovery languages](customize-windows-re.md): UI text for the Windows Recovery Environment (WinRE). Delivered as .cab files. Example: lp.cab, WinPE-Rejuv_fr-fr.cab, and more.
* [International settings](configure-international-settings-in-windows.md): Specify the default language, locale, and keyboard values during deployment or after Windows is installed.
  - List of [default input profiles (input locales)](default-input-locales-for-windows-language-packs.md). Input profiles combine the language of the input entered and the keyboard identifier.
  - List of [keyboard identifiers and input method editors (IME)](windows-language-pack-default-values.md)
  - List of [default time zones](default-time-zones.md) 
* [Out of Box Experience (OOBE)](how-oobexml-works.md): Create localized versions of end user license agreements (EULA), registration pages, and instructions for pairing keyboards and mice.
* [Retail demo experience](https://docs.microsoft.com/windows-hardware/customize/desktop/retail-demo-experience#add-retail-demo-mode-including-language-packs-to-your-images): Showcase your new devices on the retail sales floor with localized content.

## Localizing the installation process

* [Add languages to Windows Setup](add-multilingual-support-to-windows-setup.md) to create Windows installation media that works in the user's preferred language and shows the languages available in the Windows image.

* [Add languages to WinPE](winpe-mount-and-customize.md) to help your technicians install Windows in their preferred language.

* [Add languages to a Windows distribution share](add-multilingual-support-to-a-windows-distribution.md) to help users on a corporate network select Windows in their preferred language

## <span id="related_topics"></span>Related topics

* [Features On Demand](features-on-demand-v2--capabilities.md)
* Add languages to [Windows Recovery Environment (WinRE)](customize-windows-re.md)
