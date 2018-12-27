---
title: SystemLocale
description: SystemLocale
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 958580cf-a87b-49d3-a681-4a708a50bd93
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SystemLocale


`SystemLocale` specifies the default language to use for non-Unicode programs.

This setting is used by both Windows Setup and Windows Deployment Services.

The system locale specifies which bitmap fonts and code pages (for example, ANSI or DOS) are used on the system by default. The system locale setting affects only ANSI applications (non-Unicode) applications. The language for non-Unicode programs is a per-system setting.

Users can change the system locale by using the **Administrative** tab in the **Region and Language Options** item in Control Panel.

For the list of supported languages, locales, and identifiers, see [Supported Language Packs and Default Settings](http://go.microsoft.com/fwlink/p/?linkid=200317).

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
<p>The <em>System_locale</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language-region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | **SystemLocale**

## Valid Configuration Passes


windowsPE

## Applies To


For the list of the Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example shows how to set the system locale to English (United States).

```
<InputLocale>0409:00000409</InputLocale> 
<SystemLocale>en-US</SystemLocale> 
<UILanguage>en-US</UILanguage> 
<UserLocale>en-US</UserLocale>
```

## Related topics


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







