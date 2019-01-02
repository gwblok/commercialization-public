---
title: UILanguageFallback
description: UILanguageFallback
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 81a78a79-52ee-43f4-b730-1c71b755551f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UILanguageFallback


`UILanguageFallback` specifies the language that is used for resources that are not localized for the default system user interface (UI) (the [UILanguage](microsoft-windows-international-core-uilanguage.md) setting).

This setting is used by Windows Setup and Windows Deployment Services.

A fallback language is used when resources are not localized for a partially localized language. For example, Arabic is a partially localized lO

language. Only 80% of the Windows resources are localized into Arabic. The possible fallback languages for the Arabic language pack are its base languages, English and French. See the “Language pack type” column in [Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318) for details.

You only need to specify this setting if the language that [UILanguage](microsoft-windows-international-core-uilanguage.md) specifies is not fully localized and has more than one fallback language. In all other cases, this setting will be ignored.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Language_fallback</em></p></td>
<td><p>Specifies the language of the UI for resources that have not been localized into the system-preferred language.</p>
<p>The <em>Language_fallback</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p>
<p>For a list of supported languages, locales, and identifiers, see <a href="http://go.microsoft.com/fwlink/p/?linkid=200318" data-raw-source="[Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318)">Available Language Packs</a>.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md) | **UILanguageFallback**

## Valid Configuration Passes


oobeSystem

specialize

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-International-Core](microsoft-windows-international-core.md).

## XML Example


The following example shows how to set the fallback language to US English (United States).

```
<InputLocale>0401:00000401</InputLocale> 
<SystemLocale>ar-SA</SystemLocale> 
<UILanguage>ar-SA</UILanguage> 
<UILanguageFallback>en-US</UILanguageFallback> 
<UserLocale>ar-SA</UserLocale>
```

## Related topics


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







