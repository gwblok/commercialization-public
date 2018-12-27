---

Description: Explains new format for language pack file names for Windows 10 version 1607
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Where is lp.cab?

ms.date: 05/02/2017
ms.topic: article
redirect_url: https://docs.microsoft.com/windows-hardware/manufacture/desktop/language-packs-and-windows-deployment


---

# Where is lp.cab?

Language packs and language interface packs have been renamed in Windows 10 version 1607.


|         Package         |                              Name format                              |                                 Example                                 |
|-------------------------|-----------------------------------------------------------------------|-------------------------------------------------------------------------|
|      Language pack      |      Microsoft-Windows-*SKU*-Language-Pack_\_arch_\_*locale*.cab      |          Microsoft-Windows-Client-Language-Pack_x64_es-es.cab           |
| Language interface pack | Microsoft-Windows-*SKU*-Language-Interface-Pack_\_arch_\_*locale*.cab | Microsoft-Windows-Client-Language-Interface-Pack_x64_ca-es-valencia.cab |

**Note:** This change doesn't apply to WinPE, where language packs still use the name lp.cab.

## <span id="related_topics"></span>Related topics

[Language Packs](language-packs-and-windows-deployment.md)

[Available Language Packs for Windows](available-language-packs-for-windows.md)

[Features On Demand V2 (Capabilities)](features-on-demand-v2--capabilities.md)

[Windows Language Pack Default Values](windows-language-pack-default-values.md)

[Default Input Locales for Windows Language Packs](default-input-locales-for-windows-language-packs.md)
