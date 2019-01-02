---

Description: Available Language Packs for Windows
ms.assetid: ad33ff13-9777-4a97-a6b8-f4de0fda5a0c
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Available Language Packs for Windows

ms.date: 11/28/2018
ms.topic: article
ms.custom: RS5
---

# Available languages for Windows

The following tables show the supported language packs for Windows 10 and Windows Server, and supported language interface packs (LIPs) for Windows 10. LIPs are available for Windows 10, but are not available for Windows Server. For more information, see [Language packs](https://support.microsoft.com/help/14236/language-packs#lptabs=win10).

Windows 10 and Windows Server: Full language packs are not interchangeable, but some LIPs are. For example, you can add Windows 10, version 1809 LIPs to Windows Server 2019.

The version of the language, LIP, or Feature on Demand must match the version number. For example, you can neither add a Windows 10 version 1809 LIP to Windows 10 version 1803 image, nor to Windows Server 2012.

You cannot add languages to Windows 10 Home Single Language and Windows 10 Home Country Specific editions.

To learn how to add languages to Windows, or where to get them, see [Where to get language packs and LIPs](add-language-packs-to-windows.md#get-languages).

For a complete list of supported languages and locales, see [Locale Identifier Constants and Strings](https://docs.microsoft.com/en-us/windows/desktop/Intl/language-identifier-constants-and-strings).

## Supported Language Packs and Language Interface Packs

The following tables include these settings:

- **Language/region**- The name of the language that will be displayed in the UI. All 38 language packs are available for Windows 10 and Windows Server 2016. In Windows Server 2012 the user interface (UI) is localized only for the 18 languages listed in bold.
- **Language/region tag**- The language identifier based on the language tagging conventions of RFC 3066. This setting is used with the Deployment Image Servicing and Management (DISM) tool, or in an unattended answer file.
- **Language/region ID**- The hexadecimal representation of the language identifier. This setting is used with the keyboard identifier when specifying an input method using DISM.
- **Language/region decimal identifier**- The decimal representation of the language identifier. This setting is used in Oobe.xml.

## Language Packs

| Language/region | Language/region tag | Language/region ID | Language/region decimal ID | 
|---|---|---|---|
| Arabic (Saudi Arabia) | ar-SA | 0x0401 | 1025 |
| Bulgarian (Bulgaria) | bg-BG | 0x0402 | 1026 |
| Chinese (Hong Kong SAR) | zh-HK <p>*Note:* No longer used. See zh-TW.</p> | 0x0c04 | 3076 |
| **Chinese (PRC)** | zh-CN | 0x0804 | 2052 |
| **Chinese (Taiwan)** | zh-TW | 0x0404 | 1028 |
| Croatian (Croatia) | hr-HR | 0x041a | 1050 |
| **Czech (Czech Republic)** | cs-CZ | 0x0405 | 1029 |
| Danish (Denmark) | da-DK | 0x0406 | 1030 |
| **Dutch (Netherlands)** | nl-NL | 0x0413 | 1043 |
| **English (United States)** | en-US | 0x0409 | 1033 |
| English (United Kingdom) | en-GB | 0x0809 | 2057 |
| Estonian (Estonia) | et-EE | 0x0425 | 1061 |
| Finnish (Finland) | fi-FI | 0x040b | 1035 |
| French (Canada) | fr-CA | 0x0c0c | 3084 |
| **French (France)** | fr-FR | 0x040c | 1036 |
| **German (Germany)** | de-DE | 0x0407 | 1031 |
| Greek (Greece) | el-GR | 0x0408 | 1032 |
| Hebrew (Israel) | he-IL | 0x040d | 1037 |
| **Hungarian (Hungary)** | hu-HU | 0x040e | 1038 |
| **Italian (Italy)** | it-IT | 0x0410 | 1040 |
| **Japanese (Japan)** | ja-JP | 0x0411 | 1041 |
| **Korean (Korea)** | ko-KR | 0x0412 | 1042 |
| Latvian (Latvia) | lv-LV | 0x0426 | 1062 |
| Lithuanian (Lithuania) | lt-LT | 0x0427 | 1063 |
| Norwegian, Bokmål (Norway) | nb-NO | 0x0414 | 1044 |
| **Polish (Poland)** | pl-PL | 0x0415 | 1045 |
| **Portuguese (Brazil)** | pt-BR | 0x0416 | 1046 |
| **Portuguese (Portugal)** | pt-PT | 0x0816 | 2070 |
| Romanian (Romania) | ro-RO | 0x0418 | 1048 |
| **Russian (Russia)** | ru-RU | 0x0419 | 1049 |
| Serbian (Latin, Serbia) | sr-Latn-CS <p>*Note:* No longer used. See sr-Latn-RS.</p> | 0x081a | 2074 | 
| Serbian (Latin, Serbia) | sr-Latn-RS | 0x241A | 9242 |
| Slovak (Slovakia) | sk-SK | 0x041b | 1051 |
| Slovenian (Slovenia) | sl-SI | 0x0424 | 1060 |
| Spanish (Mexico) | es-MX | 0x080a | 2058 |
| **Spanish (Spain)** | es-ES | 0x0c0a | 3082 |
| **Swedish (Sweden)** | sv-SE | 0x041d | 1053 |
| Thai (Thailand) | th-TH | 0x041e | 1054 |
| **Turkish (Turkey)** | tr-TR | 0x041f | 1055 |
| Ukrainian (Ukraine) | uk-UA | 0x0422 | 1058 |


## <span id="lips"></span>Language interface packs (LIPs)

Except where noted, the following LIPs are available for Windows 10. For Windows Server, options to change keyboard and regional settings such as currency, time zones, and time/date format are available but LIPs are not available. For more information, see [Language packs](https://support.microsoft.com/help/14236/language-packs#lptabs=win10).

> [!Note]
> As of Windows 10, version 1809, LIPs are are distributed as .appx files. To learn how to add an .appx, see [Add languages to Windows](add-language-packs-to-windows.md).

| Language/region | Language/region tag | Base language/region | Language/region ID | Language/region decimal ID |
|---|---|---|---|---|
| Afrikaans (South Africa) | af-ZA | Primary: en-US <p>Secondary: en-GB</p> | 0x0436 | 1078 |
| Albanian (Albania) | sq-AL | Primary: en-US <p>Secondary: en-GB</p> | 0x041c | 1052 |
| Amharic (Ethiopia) | am-ET | Primary: en-US <p>Secondary: en-GB</p> | 0x045e | 1118 |
| Armenian (Armenia) | hy-AM | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x042b | 1067 |
| Assamese (India) | as-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x044d | 1101 |
| Azerbaijan | az-Latn-AZ | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x042c | 1068 |
| Bangla (Bangladesh) | bn-BD | Primary: en-US <p>Secondary: en-GB</p> | 0x0845 | 2117 |
| Basque (Basque) | eu-ES | Primary: es-ES <p>Secondary: en-GB, en-US, fr-FR</p> | 0x042d | 1069 |
| Belarusian | be-BY | Primary: ru-RU <p>Secondary: en-GB, en-US</p> | 0x0423 | 1059 |
| Bangla (India) | bn-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0445 | 1093 |
| Bosnian (Latin) | bs-Latn-BA | Primary: en-US <p>Secondary: en-GB, hr-HR, sr-Latn-RS</p> | 0x141a | 5146 |
| Catalan | ca-ES | Primary: es-ES <p>Secondary: en-GB, en-US, fr-FR</p> | 0x0403 | 1027 |
| Central Kurdish | ku-ARAB-IQ | Primary: en-US <p>Secondary: ar-SA, en-GB</p> | 0x0492 | 1170 |
| Cherokee | chr-CHER-US | Primary: en-US <p>Secondary: en-GB | 0x045c | 1116 |
| Dari | prs-AF | Primary: en-US <p>Secondary: en-GB</p> | 0x048c | 1164 |
| Filipino | fil-PH | Primary: en-US <p>Secondary: en-GB</p> | 0x0464 | 1124 |
| Galician | gl-ES | Primary: es-ES <p>Secondary: en-GB, en-US</p> | 0x0456 | 1110 |
| Georgian (Georgia) | ka-GE | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x0437 | 1079 |
| Gujarati (India) | gu-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0447 | 1095 |
| Hausa (Latin, Nigeria) | ha-Latn-NG | Primary: en-US <p>Secondary: en-GB, fr-FR</p> | 0x0468 | 1128 |
| Hindi (India) | hi-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0439 | 1081 |
| Icelandic (Iceland) | is-IS | Primary: en-US <p>Secondary: en-GB</p> | 0x040f | 1039 |
| Igbo (Nigeria) | ig-NG | Primary: en-US <p>Secondary: en-GB</p> | 0x0470 | 1136 |
| Indonesian (Indonesia) | id-ID | Primary: en-US <p>Secondary: en-GB</p> | 0x0421 | 1057 |
| Inuktitut (Latin, Canada) | iu-Latn-CA <p>Not available in Windows 10.</p> | Primary: en-US <p>Secondary: en-GB</p> | 0x085d | 2141 |
| Irish (Ireland) | ga-IE | Primary: en-US <p>Secondary: en-GB</p> | 0x083c | 2108 |
| isiXhosa (South Africa) | xh-ZA | Primary: en-US <p>Secondary: en-GB</p> | 0x0434 | 1076 |
| isiZulu (South Africa) | zu-ZA | Primary: en-US <p>Secondary: en-GB</p> | 0x0435 | 1077 |
| Kannada (India) | kn-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x044b | 1099 |
| Kazakh (Kazakhstan) | kk-KZ | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x043f | 1087 |
| Khmer (Cambodia) | km-KH | Primary: en-US <p>Secondary: en-GB</p> | 0x0453 | 1107 |
| K'iche' (Guatemala) | quc-Latn-GT | Primary: es-MX <p>Secondary: es-ES, en-US, en-GB</p> | 0x0486 | 1158 |
| K'iche' (Guatemala) | qut-GT <p>No longer used.</p> | Primary: es-MX <p>Secondary: es-ES, en-US, en-GB</p> | 0x0486 | 1158 |
| Kinyarwanda | rw-RW | Primary: en-US <p>Secondary: en-GB</p> | 0x0487 | 1159 |
| Kiswahili (Kenya) | sw-KE | Primary: en-US <p>Secondary: en-GB</p> | 0x0441 | 1089 |
| Konkani (India) | kok-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0457 | 1111 |
| Kyrgyz (Kyrgyzstan) | ky-KG | Primary: ru-RU <p>Secondary: en-GB, en-US</p> | 0x0440 | 1088 |
| Lao (Laos) | lo-LA | Primary: en-US <p>Secondary: en-GB</p> | 0x0454 | 1108 |
| Luxembourgish (Luxembourg) | lb-LU | Primary: fr-FR <p>Secondary: de-DE, en-GB, en-US</p> | 0x046e | 1134 |
| Macedonian (FYROM) | mk-MK | Primary: en-US <p>Secondary: en-GB</p> | 0x042f | 1071
| Malay (Malaysia, Brunei, and Singapore) | ms-MY | Primary: en-US <p>Secondary: en-GB</p> | 0x043e | 1086 |
| Malayalam (India) | ml-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x044c | 1100 |
| Maltese (Malta) | mt-MT | Primary: en-US <p>Secondary: en-GB</p> | 0x043a | 1082 |
| Maori (New Zealand) | mi-NZ | Primary: en-US <p>Secondary: en-GB</p> | 0x0481 | 1153 |
| Marathi (India) | mr-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x044e | 1102 |
| Mongolian (Cyrillic) | mn-MN | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x0450 | 1104 |
| Nepali (Federal Democratic Republic of Nepal) | ne-NP | Primary: en-US <p>Secondary: en-GB</p> | 0x0461 | 1121 |
| Norwegian, Nynorsk (Norway) | nn-NO | Primary: nb-NO <p>Secondary: en-GB, en-US</p> | 0x0814 | 2068 |
| Odia (India) | or-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0448 | 1096 |
| Persian | fa-IR | Primary: en-US <p>Secondary: en-GB</p> | 0x0429 | 1065 |
| Punjabi (India) | pa-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0446 | 1094 |
| Punjabi (Arabic) | pa-Arab-PK | Primary: en-US <p>Secondary: en-GB</p> | 0x0846 | 2118 |
| Quechua (Peru) | quz-PE | Primary: es-MX <p>Secondary: es-ES, en-GB, en-US</p> | 0x0c6b | 3179 |
| Scottish Gaelic | gd-GB | Primary: en-US <p>Secondary: en-GB</p> | 0x0491 | 1169 |
| Serbian (Cyrillic, Bosnia and Herzegovina) | sr-Cyrl-BA | Primary: en-US <p>Secondary: en-GB, sr-Latn-RS</p> | 0x1C1A | 7194 |
| Serbian (Cyrillic, Serbia) | sr-Cyrl-CS *Note:* No longer used. See sr-Latn-RS. | Primary: sr-Latn-CS <p>Secondary: en-GB, en-US</p> | 0x0c1a | 3098 |
| Serbian (Cyrillic, Serbia) | sr-Cyrl-RS | Primary: sr-Latn-RS <p>Secondary: en-GB, en-US</p> | 0x281A | 10266 |
| Sesotho sa Leboa (South Africa) | nso-ZA | Primary: en-US <p>Secondary: en-GB</p> | 0x046c | 1132 |
| Setswana (South Africa) | tn-ZA | Primary: en-US <p>Secondary: en-GB</p> | 0x0432 | 1074 |
| Sindhi (Arabic) | sd-Arab-PK | Primary: en-US <p>Secondary: en-GB</p> | 0x0859 | 2137 |
| Sinhala (Sri Lanka) | si-LK | Primary: en-US <p>Secondary: en-GB</p> | 0x045b | 1115 |
| Tajik (Cyrillic) | tg-Cyrl-TJ | Primary: ru-RU <p>Secondary: en-GB, en-US</p> | 0x0428 | 1064 |
| Tamil (India) | ta-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x0449 | 1097 |
| Tatar (Russia) | tt-RU | Primary: ru-RU <p>Secondary: en-GB, en-US</p> | 0x0444 | 1092 |
| Telugu (India) | te-IN | Primary: en-US <p>Secondary: en-GB</p> | 0x044a | 1098 |
| Tigrinya | ti-ET | Primary: en-US <p>Secondary: en-GB</p> | 0x0473 | 1139 |
| Turkmen | tk-TM | Primary: ru-RU <p>Secondary: en-GB, en-US</p> | 0x0442 | 1090 |
| Urdu | ur-PK | Primary: en-US <p>Secondary: en-GB</p> | 0x0420 | 1056 |
| Uyghur | ug-CN | Primary: zh-CN <p>Secondary: en-GB, en-US</p> | 0x0480 | 1152 |
| Uzbek (Latin) | uz-Latn-UZ | Primary: en-US <p>Secondary: en-GB, ru-RU</p> | 0x0443 | 1091 |
| Valencian | ca-ES-valencia | Primary: es-ES <p>Secondary: en-GB, en-US</p> | 0x0803 | 2051 |
| Vietnamese | vi-VN | Primary: en-US <p>Secondary: en-GB</p> | 0x042a | 1066 |
| Welsh (Great Britain) | cy-GB | Primary: en-US <p>Secondary: en-GB</p> | 0x0452 | 1106 |
| Wolof | wo-SN | Primary: fr-FR <p>Secondary: en-GB, en-US</p> | 0x0488 | 1160 |
| Yoruba (Nigeria) | yo-NG | Primary: en-US <p>Secondary: en-GB</p> | 0x046a | 1130 |

 

## Related topics

[Add Language Packs to Windows](add-language-packs-to-windows.md)

[Windows Language Pack Default Values](windows-language-pack-default-values.md)

[Default Input Locales for Windows Language Packs](default-input-locales-for-windows-language-packs.md)

 








