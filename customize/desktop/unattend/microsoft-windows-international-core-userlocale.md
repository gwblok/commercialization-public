---
title: UserLocale
description: UserLocale
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 31880e1a-2f40-4d8b-b6f0-c1799911ed39
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UserLocale


`UserLocale` specifies the per-user settings used for formatting dates, times, currency, and numbers in a Windows installation.

Users can change this value on a running Windows installation by using the **Administrative** pane in the **Region and Language** Control Panel.

For a list of supported languages, locales, and identifiers, see [Available Language Packs](http://go.microsoft.com/fwlink/?LinkId=206620).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>User_locale</em></p></td>
<td><p>Specifies the locale of the end user.</p>
<p>The <em>User_locale</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md) | **UserLocale**

## Valid Configuration Passes


oobeSystem

specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-International-Core](microsoft-windows-international-core.md).

## XML Example


The following example shows how to set the user locale to Japanese (Japan).

```
<InputLocale>0411:00000411</InputLocale> 
<SystemLocale>ja-JP</SystemLocale> 
<UILanguage>ja-JP</UILanguage> 
<UserLocale>ja-JP</UserLocale>
```

## Related topics


[Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
