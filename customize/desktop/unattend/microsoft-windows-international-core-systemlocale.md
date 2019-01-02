---
title: SystemLocale
description: SystemLocale
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 75191b23-5ced-468f-8427-97ef93828d59
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SystemLocale


`SystemLocale` specifies the default language to use for non-Unicode programs.

This setting is used by both Windows Setup and Windows Deployment Services.

The system locale specifies the bitmap fonts and code pages (ANSI or DOS) that are used on the system by default. The system locale setting affects only ANSI (non-Unicode) applications. The language for non-Unicode programs is a per-system setting.

Users can change the system locale by using the **Administrative** tab in the **Region and Language** item in Control Panel.

For the list of supported languages, locales, and identifiers, see [Supported Language Packs and Default Settings](http://go.microsoft.com/fwlink/?LinkId=206620).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>System_locale</em></p></td>
<td><p>Specifies the locale of the system.</p>
<p>The <em>System_locale</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md) | **SystemLocale**

## Valid Configuration Passes


oobeSystem

specialize

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-International-Core](microsoft-windows-international-core.md).

## XML Example


The following example shows how to set the system locale to English (United States).

```
<InputLocale>0409:00000409</InputLocale>
<SystemLocale>en-US</SystemLocale>
<UILanguage>en-US</UILanguage>
<UserLocale>en-US</UserLocale>
```

## Related topics


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)


