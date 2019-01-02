---

Description: 'Features on Demand v2 (Capabilities), introduced in Windows 10, are Windows feature packages that can be added at any time. This topic covers language and region-related FODs.'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Language and region Features on Demand'

ms.date: 12/01/2017
ms.topic: article
ms.custom: RS5
---

# Language and region Features on Demand

## <span id="language_capabilities"></span> Language and region-related Features on Demand reference

When you add a language pack to a Windows image, you also add [Features on Demand](features-on-demand-v2--capabilities.md) to enable additional functionality. To view available non-language or region-related Features on Demand, see [Available Features on Demand](features-on-demand-non-language-fod.md).

To see how to add Features on Demand and language packs to your Windows image, see [Add languages to Windows](add-and-remove-language-packs-offline-using-dism.md).

> [!div class="op_single_selector"]
> - [Languages](#language-features-on-demand)
> - [Fonts](#fonts)
> - [Additional font packages](#Additional_fonts)
> - [Region-specific requirements](#Region_requirements)

### Language Features on Demand

**Recommendation:** Add FODs after you add a language pack. Preinstall the Basic, Fonts, Text-to-speech, Optical character recognition (OCR), and speech recognition languages you expect users in the device’s target market to need. Additionally, add the handwriting recognition FODs to devices that ship with a pen.

Language Features on Demand are available in six types:

**Note:** Not all Features on Demand are available for every language. You can learn which FODs are available for languages [in the LP to FOD mapping spreadsheet](http://download.microsoft.com/download/7/6/0/7600F9DC-C296-4CF8-B92A-2D85BAFBD5D2/Windows-10-1809-FOD-to-LP-Mapping-Table.xlsx).


| Component | Sample package name | Sample capability name  | Description |
| --------- | -----------         |                   ----- | ----------- |
| Basic     | Microsoft-Windows-LanguageFeatures-Basic-fr-fr-Package.cab | Language.Basic~\~\~fr-FR~0.0.1.0  | Spell checking, text prediction, word breaking, and hyphenation if available for the language.<br></br><p>You must add this component before adding any of the other language FODs. <br></br><p>**Recommendation:** Preinstall this package for each language that you've preinstalled in an image.|
| Fonts     | Microsoft-Windows-LanguageFeatures-Fonts-Thai-Package.cab | Language.Fonts.Thai~\~\~und-THAI~0.0.1.0 | Fonts.<br></br><p>**Note:** Some languages require a font pack. For example, th-TH requires the Thai font pack.<br></br><p>Check the [list of fonts](#fonts).  |
| OCR | Microsoft-Windows-LanguageFeatures-OCR-fr-fr-Package.cab | Language.OCR~\~\~fr-FR~0.0.1.0 |  Recognizes and outputs text in an image.<br></br><p>**Recommendation:** Preinstall this package for each language that you've preinstalled in an image.<br></br><p>**Dependencies**: The basic component of the same language. |
| Handwriting recognition | Microsoft-Windows-LanguageFeatures-Handwriting-fr-fr-Package.cab | Language.Handwriting~\~\~fr-FR~0.0.1.0  | Enables handwriting recognition for devices with pen input.<br></br><p>**Recommendation:** Preinstall for the device’s target language on any device with a touch- or pen-capable screen. <br></br><p>**Dependencies**: The basic component of the same language.|
| Text-to-speech | Microsoft-Windows-LanguageFeatures-TextToSpeech-fr-fr-Package.cab| Language.TextToSpeech~\~\~fr-FR~0.0.1.0  | Enables text to speech, used by Cortana and Narrator.<br></br><p>**Recommendation:** Preinstall this package for each language that you've preinstalled in an image.</p><p>**Dependencies**: The basic component of the same language.</p> |
| Speech recognition | Microsoft-Windows-LanguageFeatures-Speech-fr-fr-Package.cab | Language.Speech~\~\~fr-FR~0.0.1.0 |  Recognizes voice input, used by Cortana and Windows Speech Recognition.<br></br><p>**Recommendation:** Preinstall this package for each language that you've preinstalled in an image.</p><p>**Dependencies**: The basic and text-to-speech components of the same language. |
| Retail Demo experience | Microsoft-Windows-RetailDemo-OfflineContent-Content-fr-fr-Package.cab | Language.RetailDemo~\~\~fr-FR~0.0.1.0 | <p>[Retail Demo experience](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/retail-demo-experience#add-retail-demo-mode-including-language-packs-to-your-images).</p><p>**Recommendation:** Preinstall this package for each language where you'll be selling devices on a retail showroom. Consider also preloading retail demo mode apps and content. </p><p>**Dependencies**: The basic component of the same languageBasic, plus the base retail demo pack: Microsoft-Windows-RetailDemo-OfflineContent-Content-Package, and the English retail demo pack: Microsoft-Windows-RetailDemo-OfflineContent-Content-en-us-Package. </p>| 



### Fonts

When adding languages for some regions, you'll need to add fonts.

Font features on demand provide additional fonts used for particular writing systems and languages. These additional fonts are not required for the Windows to display a language. However, prior to Windows 10, most of these fonts were installed by default on every system, and some were used for user interface display. Customers using particular languages are likely to require the additional fonts related to that language for documents or for user interface strings in applications that run in those languages. The capability names use script identifiers; for example, “Deva” indicates Devanagari script, which is used for Hindi, Konkani and other languages.

**Recommendation:** If a PC will be sold to a certain region, install that region's font (For example, th-TH should be preinstalled on devices shipping to regions with Thai language).

| Region      | Description                            | Font capability required                              |
|-------------|----------------------------------------|-------------------------------------------------------|
| am-ET       | Amharic                                | Microsoft-Windows-LanguageFeatures-Fonts-Ethi-Package |
| ar-SA       | Arabic (Saudi Arabia)                  | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| ar-SY       | Arabic (Syria)                         | Microsoft-Windows-LanguageFeatures-Fonts-Syrc-Package |
| as-IN       | Assamese                               | Microsoft-Windows-LanguageFeatures-Fonts-Beng-Package |
| bn-BD       | Bangla (Bangladesh)                    | Microsoft-Windows-LanguageFeatures-Fonts-Beng-Package |
| bn-IN       | Bangla (India)                         | Microsoft-Windows-LanguageFeatures-Fonts-Beng-Package |
| chr-Cher-US | Cherokee (Cherokee)                    | Microsoft-Windows-LanguageFeatures-Fonts-Cher-Package |
| fa-IR       | Persian                                | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| gu-IN       | Gujarati                               | Microsoft-Windows-LanguageFeatures-Fonts-Gujr-Package |
| he-IL       | Hebrew                                 | Microsoft-Windows-LanguageFeatures-Fonts-Hebr-Package |
| hi-IN       | Hindi                                  | Microsoft-Windows-LanguageFeatures-Fonts-Deva-Package |
| ja-JP       | Japanese                               | Microsoft-Windows-LanguageFeatures-Fonts-Jpan-Package |
| km-KH       | Khmer                                  | Microsoft-Windows-LanguageFeatures-Fonts-Khmr-Package |
| kn-IN       | Kannada                                | Microsoft-Windows-LanguageFeatures-Fonts-Knda-Package |
| kok-IN      | Konkani                                | Microsoft-Windows-LanguageFeatures-Fonts-Deva-Package |
| ko-KR       | Korean                                 | Microsoft-Windows-LanguageFeatures-Fonts-Kore-Package |
| ku-Arab-IQ  | Central Kurdish (Arabic)               | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| lo-LA       | Lao                                    | Microsoft-Windows-LanguageFeatures-Fonts-Laoo-Package |
| ml-IN       | Malayalam                              | Microsoft-Windows-LanguageFeatures-Fonts-Mlym-Package |
| mr-IN       | Marathi                                | Microsoft-Windows-LanguageFeatures-Fonts-Deva-Package |
| ne-NP       | Nepali                                 | Microsoft-Windows-LanguageFeatures-Fonts-Deva-Package |
| or-IN       | Odia                                   | Microsoft-Windows-LanguageFeatures-Fonts-Orya-Package |
| pa-Arab-PK  | Punjabi (Arabic)                       | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| pa-IN       | Punjabi                                | Microsoft-Windows-LanguageFeatures-Fonts-Guru-Package |
| prs-AF      | Dari                                   | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| sd-Arab-PK  | Sindhi (Arabic)                        | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| si-LK       | Sinhala                                | Microsoft-Windows-LanguageFeatures-Fonts-Sinh-Package |
| syr-SY      | Syriac                                 | Microsoft-Windows-LanguageFeatures-Fonts-Syrc-Package |
| ta-IN       | Tamil                                  | Microsoft-Windows-LanguageFeatures-Fonts-Taml-Package |
| te-IN       | Telugu                                 | Microsoft-Windows-LanguageFeatures-Fonts-Telu-Package |
| th-TH       | Thai                                   | Microsoft-Windows-LanguageFeatures-Fonts-Thai-Package |
| ti-ET       | Tigrinya                               | Microsoft-Windows-LanguageFeatures-Fonts-Ethi-Package |
| ug-CN       | Uyghur                                 | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| ur-PK       | Urdu                                   | Microsoft-Windows-LanguageFeatures-Fonts-Arab-Package |
| zh-CN       | Chinese (Simplified)                   | Microsoft-Windows-LanguageFeatures-Fonts-Hans-Package |
| zh-TW       | Chinese Traditional (Hong Kong, Macau and Taiwan)          | Microsoft-Windows-LanguageFeatures-Fonts-Hant-Package |

### <span id="Additional_fonts"></span><span id="additional_fonts"></span> Additional fonts available

These fonts are optional and not required for any region.

| Name      | Description  |
|----------|------------|
| Microsoft-Windows-LanguageFeatures-Fonts-PanEuropeanSupplementalFonts-Package | Pan-European Supplemental Fonts. Includes additional fonts: Arial Nova, Georgia Pro, Gill Sans Nova, Neue Haas Grotesk, Rockwell Nova, Verdana Pro. |

### <span id="Region_requirements"></span><span id="region_requirements"></span> Other region-specific requirements

| Region | Package                               | Description        | Recommendation                                                                                                     |
|--------|-------------------------------|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---|
| zh-TW  | Microsoft-Windows-InternationalFeatures-Taiwan-Package\~31bf3856ad364e35\~amd64~~.cab  | Supplemental support for Taiwan date formatting requirements.  Package will be provided to customers located in Taiwan. | Preinstall only on devices shipping to the Taiwan market. Not installing this capability on devices causes any API calls to that use the Taiwan calendar to fail. |

Note that this feature is distributed as a .cab file on the Feature on Demand ISO. Use `DISM /add-package` to add it to your image. See [Add or remove packages offline with DISM](add-or-remove-packages-offline-using-dism.md) for more information.

### List of all language-related Features on Demand
[Download the list of all available language FODs](http://download.microsoft.com/download/7/6/0/7600F9DC-C296-4CF8-B92A-2D85BAFBD5D2/Windows-10-1809-FOD-to-LP-Mapping-Table.xlsx)

## <span id="related_topics"></span>Related topics

[Available Features on Demand](#features-on-demand-non-language-fod.md)

[Add Language Packs to Windows](add-language-packs-to-windows.md)

[DISM Capabilities Package Servicing Command-Line Options](dism-capabilities-package-servicing-command-line-options.md)
