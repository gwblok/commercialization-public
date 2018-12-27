---
title: UILanguage
description: UILanguage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 125ef536-740c-46f1-8ecc-4e47cd79cc4e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UILanguage


`UILanguage` specifies the default system language that is used to display user interface (UI) items (such as menus, dialog boxes, and Help files).

For a list of supported languages, see [Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318).

In upgrade installation types, this setting is ignored. In upgrade installations, you can upgrade only from the same language.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>UI_language</em></p></td>
<td><p>Specifies the language of the UI.</p>
<p><em>UI_language</em> is a string based on the language-tagging conventions of RFC 3066. The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md) | **UILanguage**

## Valid Configuration Passes


oobeSystem

specialize

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-International-Core](microsoft-windows-international-core.md).

## XML Example


The following example shows how to set the UI language to German (Germany).

```
<InputLocale>0407:00000407</InputLocale>
<SystemLocale>de-DE</SystemLocale>
<UILanguage>de-DE</UILanguage>
<UserLocale>de-DE</UserLocale>
```

## Related topics


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)

