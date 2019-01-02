---

Description: 'Input profiles (or input locales) describe the language of the input entered, and the keyboard on which it is being entered. When the first user logs into Windows and identifies their region, Windows sets the input profiles.'
ms.assetid: 0bae00b5-dfcb-472e-a271-07ef62ad5fc5
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Default Input Profiles (Input Locales) in Windows'

ms.date: 05/02/2017
ms.topic: article


---

# Default Input Profiles (Input Locales) in Windows


Input profiles (or input locales) describe the language of the input entered, and the keyboard on which it is being entered. When the first user logs into Windows and identifies their region, Windows sets the input profiles.

The input profiles are made up of a [language identifier](http://go.microsoft.com/fwlink/?LinkId=63026) and a [keyboard identifier](windows-language-pack-default-values.md). For example, the Arabic (Algerian) input profile is 1401:00020401, where 1401 is the hexadecimal identifier of the language: Arabic (Algeria) and 00020401 is the hexadecimal identifier of the keyboard: Arabic 101.

When the user first identifies the time and date format (User Locale) as Algeria, Windows sets up both the primary input profile, and a secondary input profile: French (France) with French keyboard. The secondary input profile can help the user by providing a keyboard with a Latin character set for tasks that require it, such as filling out email addresses. Some character sets (like CHS IME) have a Latin character set built in.

Windows uses the language component of the input profile for tasks like spelling, hyphenation, and text prediction of the intended key press when using the touch-screen keyboard.

When setting up new devices for your users, you can use the DISM commands: /Set-InputLocale or /Set-AllIntl to identify a default input profile. You can either select the input profile by its language and keyboard pair (1401:00020401) or you can use a language/region tag to receive the default settings for that language/region.

Examples:

```
Dism /Image:"C:\mount\windows" /Set-InputLocale:042d:0000040a
Dism /Image:"C:\mount\windows" /Set-InputLocale:0411:{03B5835F-F03C-411B-9CE2-AA23E1171E36}{A76C93D9-5523-4E90-AAFA-4DB112F9AC76}
Dism /Image:"C:\mount\windows" /Set-InputLocale:id-ID
Dism /Image:"C:\mount\windows" /Set-AllIntl:fr-FR
```

For a list of language/region names, see [Available Language Packs for Windows](available-language-packs-for-windows.md).

<table>
<thead valign="bottom" align="left">
<tr class="header">
<th>Language/Region</th>
<th>Primary input profile (language and keyboard pair)</th>
<th>Secondary input profile</th>
</tr>
</thead>
<tbody valign="top" align="left">
<tr class="odd">
<td>Afrikaans - South Africa</td>
<td>af-ZA: United States - English (0436:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Albanian - Albania</td>
<td>sq-AL: Albanian (041c:0000041c)</td>
<td></td>
</tr>
<tr class="odd">
<td>Alsatian - France</td>
<td>gsw-FR: French (0484:0000040c)</td>
<td></td>
</tr>
<tr class="even">
<td>Amharic - Ethiopia</td>
<td>am-ET: Amharic Input Method (045e:{E429B25A-E5D3-4D1F-9BE3-0C608477E3A1}{8F96574E-C86C-4bd6-9666-3F7327D4CBE8})</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Algeria</td>
<td>ar-DZ: Arabic (102) AZERTY (1401:00020401)</td>
<td>fr-FR: French (040c:0000040c)</td>
</tr>
<tr class="even">
<td>Arabic - Bahrain</td>
<td>ar-BH: Arabic (101) (3c01:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Egypt</td>
<td>ar-EG: Arabic (101) (0c01:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Iraq</td>
<td>ar-IQ: Arabic (101) (0801:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Jordan</td>
<td>ar-JO: Arabic (101) (2c01:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Kuwait</td>
<td>ar-KW: Arabic (101) (3401:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Lebanon</td>
<td>ar-LB: Arabic (101) (3001:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Libya</td>
<td>ar-LY: Arabic (101) (1001:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Morocco</td>
<td>ar-MA: Arabic (102) AZERTY (1801:00020401)</td>
<td>fr-FR: French (040c:0000040c)</td>
</tr>
<tr class="even">
<td>Arabic - Oman</td>
<td>ar-OM: Arabic (101) (2001:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Qatar</td>
<td>ar-QA: Arabic (101) (4001:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Saudi Arabia</td>
<td>ar-SA: Arabic (101) (0401:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Arabic - Syria</td>
<td>ar-SY: Arabic (101) (2801:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Tunisia</td>
<td>ar-TN: Arabic (102) AZERTY (1c01:00020401)</td>
<td>fr-FR: French (040c:0000040c)</td>
</tr>
<tr class="odd">
<td>Arabic - U.A.E.</td>
<td>ar-AE: Arabic (101) (3801:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Arabic - Yemen</td>
<td>ar-YE: Arabic (101) (2401:00000401)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Armenian - Armenia</td>
<td>hy-AM: Armenian Phonetic (042b:0002042b)</td>
<td><p>hy-AM: Armenian Typewriter (042b:0003042b)</p>
<p>ru-RU: Russian (0419:00000419)</p></td>
</tr>
<tr class="even">
<td>Assamese - India</td>
<td>as-IN: Assamese - Inscript (044d:0000044d)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Azerbaijani - Azerbaijan (Cyrillic)</td>
<td>az-Cyrl-AZ: Azerbaijani Cyrillic (082c:0000082c)</td>
<td><p>en-US: United States - English (0409:00000409)</p>
<p>az-Latn-AZ: Azeri Latin (042c:0000042c)</p></td>
</tr>
<tr class="even">
<td>Azerbaijani - Azerbaijan (Latin)</td>
<td>az-Latn-AZ: Azerbaijani Latin (042c:0000042c)</td>
<td><p>en-US: United States - English (0409:00000409)</p>
<p>az-Cyrl-AZ: Azeri Cyrillic (082c:0000082c)</p></td>
</tr>
<tr class="odd">
<td>Bangla (Bangladesh)</td>
<td>bn-BD: Bangla - Bangladesh (0845:00000445)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Bangla - India (Bengali Script)</td>
<td>bn-IN: Bangla India-INSCRIPT (0445:00020445)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Bashkir - Russia</td>
<td>ba-RU: Bashkir (046d:0000046d)</td>
<td><p>ru-RU Russian (0419:00000419)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="even">
<td>Basque - Basque</td>
<td>eu-ES: Spanish (042d:0000040a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Belarusian - Belarus</td>
<td>be-BY: Belarusian (0423:00000423)</td>
<td><p>ru-RU: Russian (0419:00000419)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="even">
<td>Bosnian - Bosnia and Herzegovina (Cyrillic)</td>
<td>bs-Cyrl-BA: Bosnian (Cyrillic) (201a:0000201a)</td>
<td>bs-Latn-BA: Croatian (141a:0000041a)</td>
</tr>
<tr class="odd">
<td>Bosnian - Bosnia and Herzegovina (Latin)</td>
<td>bs-Latn-BA: Croatian (141a:0000041a)</td>
<td></td>
</tr>
<tr class="even">
<td>Breton - France</td>
<td>br-FR: French (047e:0000040c)</td>
<td></td>
</tr>
<tr class="odd">
<td>Bulgarian - Bulgaria</td>
<td>bg-BG: Bulgarian (0402:00030402)</td>
<td>en-US: United States - International (0409:00020409)</td>
</tr>
<tr class="even">
<td>Burmese - Myanmar</td>
<td>my-MM: Myanmar (0455:00010c00)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Catalan - Catalan</td>
<td>ca-ES: Spanish (0403:0000040a)</td>
<td></td>
</tr>
<tr class="even">
<td>Central Atlas Tamazight (Latin) - Algeria</td>
<td>fr-FR: French (040c:0000040c)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Central Atlas Tamazight (Latin) - Algeria</td>
<td>tzm-Latn-DZ: Central Atlas Tamazight (085f:0000085f)</td>
<td></td>
</tr>
<tr class="even">
<td>Central Atlas Tamazight (Tifinagh) - Morocco</td>
<td>tzm-Tfng-MA: (105f:0000105f)</td>
<td>fr-FR: French (040c:0000040c)</td>
</tr>
<tr class="odd">
<td>Central Kurdish (Iraq)</td>
<td>ku-Arab-IQ: (0492:00000492)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Cherokee (Cherokee, United States)</td>
<td>chr-Cher-US: Cherokee Nation (045c:0000045c)</td>
<td><p>Cherokee Nation Phonetic (045c:0001045c)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="odd">
<td>Chinese - PRC</td>
<td>zh-CN: Microsoft Pinyin - Simple Fast (0804:{81D4E9C9-1D3B-41BC-9E6C-4B40BF79E35E}{FA550B04-5AD7-411f-A5AC-CA038EC515D7})</td>
<td></td>
</tr>
<tr class="even">
<td>Chinese - Taiwan</td>
<td>zh-TW: Chinese (Traditional) - New Phonetic (0404:{B115690A-EA02-48D5-A231-E3578D2FDF80}{B2F9C502-1742-11D4-9790-0080C882687E})</td>
<td></td>
</tr>
<tr class="odd">
<td>Corsican - France</td>
<td>co-FR: French (0483:0000040c)</td>
<td></td>
</tr>
<tr class="even">
<td>Croatian - Bosnia and Herzegovina</td>
<td>hr-BA: Croatian (101a:0000041a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Croatian - Croatia</td>
<td>hr-HR: Croatian (041a:0000041a)</td>
<td></td>
</tr>
<tr class="even">
<td>Czech - Czech Republic</td>
<td>cs-CZ: Czech (0405:00000405)</td>
<td></td>
</tr>
<tr class="odd">
<td>Danish - Denmark</td>
<td>da-DK: Danish (0406:00000406)</td>
<td>en-US: Danish (0409:00000406)</td>
</tr>
<tr class="even">
<td>Dari - Afghanistan</td>
<td>prs-AF: Persian (Standard) (048c:00050429)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Divehi - Maldives</td>
<td>dv-MV: Divehi Phonetic (0465:00000465)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Dutch - Belgium</td>
<td>nl-BE: Belgian (Period) (0813:00000813)</td>
<td></td>
</tr>
<tr class="odd">
<td>Dutch - Netherlands</td>
<td>nl-NL: United States - International (0413:00020409)</td>
<td></td>
</tr>
<tr class="even">
<td>Dzongkha</td>
<td>dz-BT: 0C51:00000C51;0409:00000409</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>English - Australia</td>
<td>en-AU: United States - English (0c09:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Belize</td>
<td>en-BZ: United States - English (2809:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - Canada</td>
<td>en-CA: United States - English (1009:00000409)</td>
<td>en-CA: Canadian Multilingual Standard (1009:00011009)</td>
</tr>
<tr class="even">
<td>English - Caribbean</td>
<td>en-029: United States - English (2409:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - India</td>
<td>en-IN: India (4009:00004009)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Ireland</td>
<td>en-IE: Irish (1809:00001809)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - Jamaica</td>
<td>en-JM: United States - English (2009:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Malaysia</td>
<td>en-MY: United States - English (4409:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - New Zealand</td>
<td>en-NZ: United States - English (1409:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Philippines</td>
<td>en-PH: United States - English (3409:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - Singapore</td>
<td>en-SG: United States - English (4809:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - South Africa</td>
<td>en-ZA: United States - English (1c09:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - Trinidad</td>
<td>en-TT: United States - English (2c09:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Great Britain</td>
<td>en-GB: Great Britain (0809:00000809)</td>
<td></td>
</tr>
<tr class="odd">
<td>English - United States</td>
<td>en-US: United States - English (0409:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>English - Zimbabwe</td>
<td>en-ZW: United States - English (3009:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>Estonian - Estonia</td>
<td>et-EE: Estonian (0425:00000425)</td>
<td></td>
</tr>
<tr class="even">
<td>Faroese - Faroe Islands</td>
<td>fo-FO: Danish (0438:00000406)</td>
<td></td>
</tr>
<tr class="odd">
<td>Filipino - Philippines</td>
<td>fil-PH: United States - English (0464:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Finnish - Finland</td>
<td>fi-FI: Finnish (040b:0000040b)</td>
<td></td>
</tr>
<tr class="odd">
<td>French - Belgium</td>
<td>fr-BE: Belgian French (080c:0000080c)</td>
<td></td>
</tr>
<tr class="even">
<td>French - Canada</td>
<td>fr-CA: Canadian Multilingual Standard (0c0c:00011009)</td>
<td>en-CA: Canadian Multilingual Standard (1009:00011009)</td>
</tr>
<tr class="odd">
<td>French - France</td>
<td>fr-FR: French (040c:0000040c)</td>
<td></td>
</tr>
<tr class="even">
<td>French - Luxembourg</td>
<td>fr-LU: Swiss French (140c:0000100C)</td>
<td>fr-LU: French (140c:0000040c)</td>
</tr>
<tr class="odd">
<td>French - Monaco</td>
<td>fr-MC: French (180c:0000040c)</td>
<td></td>
</tr>
<tr class="even">
<td>French - Switzerland</td>
<td>fr-CH: Swiss French (100c:0000100c)</td>
<td>de-CH: Swiss German (0807:00000807)</td>
</tr>
<tr class="odd">
<td>Frisian - Netherlands</td>
<td>fy-NL: United States - International (0462:00020409)</td>
<td></td>
</tr>
<tr class="even">
<td>Fulah (Latin, Senegal)</td>
<td>ff-Latn-SN: Wolof (0867:00000488)</td>
<td></td>
</tr>
<tr class="odd">
<td>Galician - Galician</td>
<td>gl-ES: Spanish (0456:0000040a)</td>
<td></td>
</tr>
<tr class="even">
<td>Georgian - Georgia</td>
<td>ka-GE: Georgian (QWERTY) (0437:00010437)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>German - Austria</td>
<td>de-AT: German (0c07:00000407)</td>
<td>de-AT: German ()</td>
</tr>
<tr class="even">
<td>German - Germany</td>
<td>de-DE: German (0407:00000407)</td>
<td>de-DE: German ()</td>
</tr>
<tr class="odd">
<td>German - Liechtenstein</td>
<td>de-LI: Swiss German (1407:00000807)</td>
<td></td>
</tr>
<tr class="even">
<td>German - Luxembourg</td>
<td>de-LU: German (1007:00000407)</td>
<td></td>
</tr>
<tr class="odd">
<td>German - Switzerland</td>
<td>de-CH: Swiss German (0807:00000807)</td>
<td>fr-CH: Swiss French (100C:0000100C)</td>
</tr>
<tr class="even">
<td>Greek - Greece</td>
<td>el-GR: Greek (0408:00000408)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Greenlandic - Greenland</td>
<td>kl-GL: Danish (046f:00000406)</td>
<td></td>
</tr>
<tr class="even">
<td>Guarani - Paraguay</td>
<td>gn-PY: Guarani (0474:00000474)</td>
<td></td>
</tr>
<tr class="odd">
<td>Gujarati - India (Gujarati Script)</td>
<td>gu-IN: Gujarati (0447:00000447)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Hausa (Latin) - Nigeria</td>
<td>ha-Latn-NG: Hausa (0468:00000468)</td>
<td></td>
</tr>
<tr class="odd">
<td>Hawaiian - United States</td>
<td>haw-US: (0475:00000475)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Hebrew - Israel</td>
<td>he-IL: (040d:0002040d)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Hindi - India</td>
<td>hi-IN: Hindi Traditional (0439:00010439)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Hungarian - Hungary</td>
<td>hu-HU: Hungarian (040e:0000040e)</td>
<td></td>
</tr>
<tr class="odd">
<td>Icelandic - Iceland</td>
<td>is-IS: Icelandic (040f:0000040f)</td>
<td></td>
</tr>
<tr class="even">
<td>Igbo - Nigeria</td>
<td>ig-NG: Igbo (0470:00000470)</td>
<td></td>
</tr>
<tr class="odd">
<td>Inari Sami - Finland</td>
<td>smn-FI: Finnish with Sami (243b:0001083b)</td>
<td></td>
</tr>
<tr class="even">
<td>Indonesian - Indonesia</td>
<td>id-ID: United States - English (0421:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>Inuktitut (Latin) - Canada</td>
<td>iu-Latn-CA: Inuktitut - Latin (085d:0000085d)</td>
<td>en-CA: United States - English (1009:00000409)</td>
</tr>
<tr class="even">
<td>Inuktitut (Syllabics) - Canada</td>
<td>iu-Cans-CA: Inuktitut - Naqittaut (045d:0001045d)</td>
<td>en-CA: United States - English (1009:00000409)</td>
</tr>
<tr class="odd">
<td>Irish - Ireland</td>
<td>ga-IE: Irish (083c:00001809)</td>
<td></td>
</tr>
<tr class="even">
<td>isiXhosa / Xhosa - South Africa</td>
<td>xh-ZA: United States - English (0434:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>isiZulu / Zulu - South Africa</td>
<td>zu-ZA: United States - English (0435:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Italian - Italy</td>
<td>it-IT: Italian (0410:00000410)</td>
<td></td>
</tr>
<tr class="odd">
<td>Italian - Switzerland</td>
<td>it-CH: Swiss French (0810:0000100c)</td>
<td>it-CH: Italian (0810:00000410)</td>
</tr>
<tr class="even">
<td>Japanese - Japan</td>
<td>ja-JP: Microsoft IME (0411:{03B5835F-F03C-411B-9CE2-AA23E1171E36}{A76C93D9-5523-4E90-AAFA-4DB112F9AC76})</td>
<td></td>
</tr>
<tr class="odd">
<td>Javanese (Latin) - Indonesia</td>
<td>jv-Latn-ID: US (0c00:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Kannada - India (Kannada Script)</td>
<td>kn-IN: Kannada (044b:0000044b)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Kazakh - Kazakhstan</td>
<td>kk-KZ: Kazakh (043f:0000043f)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Khmer - Cambodia</td>
<td>km-KH: Khmer (0453:00000453)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>K&#39;iche - Guatemala</td>
<td>qut-GT: Latin American (0486:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Kinyarwanda - Rwanda</td>
<td>rw-RW: United States - English (0487:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>Konkani - India</td>
<td>kok-IN: Devanagari-INSCRIPT (0457:00000439)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Korean(Extended Wansung) - Korea</td>
<td>ko-KR: Microsoft IME (0412:{A028AE76-01B1-46C2-99C4-ACD9858AE02F}{B5FE1F02-D5F2-4445-9C03-C568F23C99A1})</td>
<td></td>
</tr>
<tr class="odd">
<td>Kyrgyz - Kyrgyzstan</td>
<td>ky-KG: Kyrgyz Cyrillic (0440:00000440)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Lao - Lao PDR</td>
<td>lo-LA: Lao (0454:00000454)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Latvian - Legacy</td>
<td>lv-LV: Latvian (QWERTY) (0426:00010426)</td>
<td></td>
</tr>
<tr class="even">
<td>Latvian - Standard</td>
<td>lv-LV: Latvian (Standard) (0426:00020426)</td>
<td></td>
</tr>
<tr class="odd">
<td>Lithuanian - Lithuania</td>
<td>lt-LT: Lithuanian (0427:00010427)</td>
<td></td>
</tr>
<tr class="even">
<td>Lower Sorbian - Germany</td>
<td>dsb-DE: Sorbian Standard (082e:0002042e)</td>
<td></td>
</tr>
<tr class="odd">
<td>Lule Sami - Norway</td>
<td>smj-NO: Norwegian with Sami (103b:0000043b)</td>
<td></td>
</tr>
<tr class="even">
<td>Lule Sami - Sweden</td>
<td>smj-SE: Swedish with Sami (143b:0000083b)</td>
<td></td>
</tr>
<tr class="odd">
<td>Luxembourgish - Luxembourg</td>
<td>lb-LU: Luxembourgish (046e:0000046e)</td>
<td></td>
</tr>
<tr class="even">
<td>Macedonian - F.Y.R.O.M</td>
<td>mk-MK: Macedonia (FYROM) - Standard (042f:0001042f)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Malay - Brunei</td>
<td>ms-BN: United States - English (083e:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Malay - Malaysia</td>
<td>ms-MY: United States - English (043e:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>Malayalam - India (Malayalam Script)</td>
<td>ml-IN: Malayalam (044c:0000044c)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Maltese - Malta</td>
<td>mt-MT: Maltese 47-Key (043a:0000043a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Maori - New Zealand</td>
<td>mi-NZ: Maori (0481:00000481)</td>
<td>en-NZ: United States - English (1409:00000409)</td>
</tr>
<tr class="even">
<td>Mapudungun - Chile</td>
<td>arn-CL: Latin American (047a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Marathi - India</td>
<td>mr-IN: Marathi (044e:0000044e)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Mohawk - Mohawk</td>
<td>moh-CA: United States - English (047c:00000409)</td>
<td></td>
</tr>
<tr class="odd">
<td>Mongolian (Cyrillic) - Mongolia</td>
<td>mn-MN: Mongolian Cyrillic (0450:00000450)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Mongolian (Mongolian) - Mongolia</td>
<td>mn-Mong-MN: Traditional Mongolian (Standard) (0c50:00010850)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Mongolian (Mongolian – PRC – Legacy)</td>
<td>mn-Mong-CN: Mongolian (Mongolian Script) (0850:00000850)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Mongolian (Mongolian– PRC – Standard)</td>
<td>mn-Mong-CN: Mongolian (Mongolian Script) (0850:00010850)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>N&#39;ko – Guinea</td>
<td>nqo-GN: N’Ko (0c00:00090C00)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Nepali - Federal Democratic Republic of Nepal</td>
<td>ne-NP: Nepali (0461:00000461)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Northern Sami - Finland</td>
<td>se-FI: Finnish with Sami (0c3b:0001083b)</td>
<td></td>
</tr>
<tr class="even">
<td>Northern Sami - Norway</td>
<td>se-NO: Norwegian with Sami (043b:0000043b)</td>
<td></td>
</tr>
<tr class="odd">
<td>Northern Sami - Sweden</td>
<td>se-SE: Swedish with Sami (083b:0000083b)</td>
<td></td>
</tr>
<tr class="even">
<td>Norwegian - Norway (Bokmål)</td>
<td>nb-NO: Norwegian (0414:00000414)</td>
<td></td>
</tr>
<tr class="odd">
<td>Norwegian - Norway (Nynorsk)</td>
<td>nn-NO: Norwegian (0814:00000414)</td>
<td></td>
</tr>
<tr class="even">
<td>Occitan - France</td>
<td>oc-FR: French (0482:0000040c)</td>
<td></td>
</tr>
<tr class="odd">
<td>Odia - India (Odia Script)</td>
<td>or-IN: Odia (0448:00000448)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Pashto - Afghanistan</td>
<td>ps-AF: Pashto (Afghanistan) (0463:00000463)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Persian</td>
<td>fa-IR: Central Kurdish (0429:00000429)</td>
<td><p>Fa-IR: Persian (Standard) (0429:00050429)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="even">
<td>Polish - Poland</td>
<td>pl-PL: Polish (Programmers) (0415:00000415)</td>
<td></td>
</tr>
<tr class="odd">
<td>Portuguese - Brazil</td>
<td>pt-BR: Portuguese (Brazilian ABNT) (0416:00000416)</td>
<td></td>
</tr>
<tr class="even">
<td>Portuguese - Portugal</td>
<td>pt-PT: Portuguese (0816:00000816)</td>
<td></td>
</tr>
<tr class="odd">
<td>Punjabi - India (Gurmukhi Script)</td>
<td>pa-IN: Punjabi (0446:00000446)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Punjabi (Islamic Republic of Pakistan)</td>
<td>pa-Arab-PK: Urdu (0846:00000420)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Quechua - Bolivia</td>
<td>quz-BO: Latin American (046b:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Quechua - Ecuador</td>
<td>quz-EC: Latin American (086b:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Quechua - Peru</td>
<td>quz-PE: Latin American (0c6b:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Romanian - Romania</td>
<td>ro-RO: Romanian (Standard) (0418:00010418)</td>
<td></td>
</tr>
<tr class="odd">
<td>Romansh - Switzerland</td>
<td>rm-CH: Swiss German (0417:00000807)</td>
<td></td>
</tr>
<tr class="even">
<td>Russian - Russia</td>
<td>ru-RU: Russian (0419:00000419)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Sakha - Russia</td>
<td>sah-RU: Sakha (0485:00000485)</td>
<td><p>ru-RU Russian (0419:00000419)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="even">
<td>Sanskrit - India</td>
<td>sa-IN: Devanagari-INSCRIPT (044f:00000439)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Scottish Gaelic - Great Britain</td>
<td>gd-GB: Gaelic (0491:00011809)</td>
<td></td>
</tr>
<tr class="even">
<td>Serbian - Bosnia and Herzegovina (Cyrillic)</td>
<td>sr-Cyrl-BA: Serbian (Cyrillic) (1c1a:00000c1a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Serbian - Bosnia and Herzegovina (Latin)</td>
<td>sr-Latn-BA: Serbian (Latin) (181a:0000081a)</td>
<td></td>
</tr>
<tr class="even">
<td>Serbian - Montenegro (Cyrillic)</td>
<td>sr-Cyrl-ME: Serbian (Cyrillic) (301a:00000c1a)</td>
<td>en-US: United States - International (0409:00020409)</td>
</tr>
<tr class="odd">
<td>Serbian - Montenegro (Latin)</td>
<td>sr-Latn-ME: Serbian (Latin) (2c1a:0000081a)</td>
<td></td>
</tr>
<tr class="even">
<td>Serbian - Serbia (Cyrillic)</td>
<td>sr-Cyrl-RS: Serbian (Cyrillic) (281a:00000c1a)</td>
<td>en-US: United States - International (0409:00020409)</td>
</tr>
<tr class="odd">
<td>Serbian - Serbia (Latin)</td>
<td>sr-Latn-RS: Serbian (Latin) (241a:0000081a)</td>
<td></td>
</tr>
<tr class="even">
<td>Serbian - Serbia and Montenegro (Former) (Cyrillic)</td>
<td>sr-Cyrl-CS: Serbian (Cyrillic) (0c1a:00000c1a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Serbian - Serbia and Montenegro (Former) (Latin)</td>
<td>sr-Latn-CS: Serbian (Latin) (081a:0000081a)</td>
<td></td>
</tr>
<tr class="even">
<td>Sesotho sa Leboa / Northern Sotho - South Africa</td>
<td>nso-ZA: Sesotho sa Leboa (046c:0000046c)</td>
<td></td>
</tr>
<tr class="odd">
<td>Setswana / Tswana - Botswana</td>
<td>tn-BW: Setswana (0832:00000432)</td>
<td></td>
</tr>
<tr class="even">
<td>Setswana / Tswana - South Africa</td>
<td>tn-ZA: Setswana (0432:00000432)</td>
<td></td>
</tr>
<tr class="odd">
<td>Shona – Zimbabwe</td>
<td>sn-Latn-ZW: US (0c00:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Sindhi (Islamic Republic of Pakistan)</td>
<td>sd-Arab-PK: Urdu (0859:00000420)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Sinhala - Sri Lanka</td>
<td>si-LK: Sinhala (045b:0000045b)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Skolt Sami - Finland</td>
<td>sms-FI: Finnish with Sami (203b:0001083b)</td>
<td></td>
</tr>
<tr class="odd">
<td>Slovak - Slovakia</td>
<td>sk-SK: Slovak (041b:0000041b)</td>
<td></td>
</tr>
<tr class="even">
<td>Slovenian - Slovenia</td>
<td>sl-SI: Slovenian (0424:00000424)</td>
<td></td>
</tr>
<tr class="odd">
<td>Southern Sami - Norway</td>
<td>sma-NO: Norwegian with Sami (183b:0000043b)</td>
<td></td>
</tr>
<tr class="even">
<td>Southern Sami - Sweden</td>
<td>sma-SE: Swedish with Sami (1c3b:0000083b)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Argentina</td>
<td>es-AR: Latin American (2c0a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Bolivarian Republic of Venezuela</td>
<td>es-VE: Latin American (200a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Bolivia</td>
<td>es-BO: Latin American (400a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Chile</td>
<td>es-CL: Latin American (340a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Colombia</td>
<td>es-CO: Latin American (240a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Costa Rica</td>
<td>es-CR: Latin American (140a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Dominican Republic</td>
<td>es-DO: Latin American (1c0a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Ecuador</td>
<td>es-EC: Latin American (300a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - El Salvador</td>
<td>es-SV: Latin American (440a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Guatemala</td>
<td>es-GT: Latin American (100a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Honduras</td>
<td>es-HN: Latin American (480a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Latin America</td>
<td>es-419: Latin American (580a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Mexico</td>
<td>es-MX: Latin American (080a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Nicaragua</td>
<td>es-NI: Latin American (4c0a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Panama</td>
<td>es-PA: Latin American (180a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Paraguay</td>
<td>es-PY: Latin American (3c0a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Peru</td>
<td>es-PE: Latin American (280a:0000080a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Spanish - Commonwealth of Puerto Rico</td>
<td>es-PR: Latin American (500a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - Spain (International Sort)</td>
<td>es-ES: Spanish (0c0a:0000040a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Spanish - Spain (Traditional Sort)</td>
<td>es-ES_tradnl: Spanish (040a:0000040a)</td>
<td></td>
</tr>
<tr class="even">
<td>Spanish - United States</td>
<td>es-US: Latin American (540a:0000080a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Spanish - Uruguay</td>
<td>es-UY: Latin American (380a:0000080a)</td>
<td></td>
</tr>
<tr class="even">
<td>Standard Moroccan Tamazight - Morocco</td>
<td>zgh-Tfng-MA: Tifinagh (Basic) (0c00:0000105F)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Swahili - Kenya</td>
<td>sw-KE: United States - English (0441:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Swedish - Finland</td>
<td>sv-FI: Swedish (081d:0000041d)</td>
<td></td>
</tr>
<tr class="odd">
<td>Swedish - Sweden</td>
<td>sv-SE: Swedish (041d:0000041d)</td>
<td></td>
</tr>
<tr class="even">
<td>Syriac - Syria</td>
<td>syr-SY: Syriac (045a:0000045a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Tajik - Tajikistan</td>
<td>tg-Cyrl-TJ: Tajik (0428:00000428)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Tamil - India</td>
<td>ta-IN: Tamil (0449:00000449)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Tamil - Sri Lanka</td>
<td>ta-LK: Tamil (0849:00000449)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Tatar – Russia (Legacy)</td>
<td>tt-RU: Tatar (0444:00000444)</td>
<td><p>ru-RU: Russian (0419:00000419)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="odd">
<td>Tatar – Russia (Standard)</td>
<td>tt-RU: Tatar (0444:00010444)</td>
<td><p>ru-RU: Russian (0419:00000419)</p>
<p>en-US: United States - English (0409:00000409)</p></td>
</tr>
<tr class="even">
<td>Telugu - India (Telugu Script)</td>
<td>te-IN: Telugu (044a:0000044a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Thai - Thailand</td>
<td>th-TH: Thai Kedmanee (041e:0000041e)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Tibetan - PRC</td>
<td>bo-CN: Tibetan (PRC) (0451:00010451)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Tigrinya (Eritrea)</td>
<td>ti-ET: Tigrinya Input Method (0473:{E429B25A-E5D3-4D1F-9BE3-0C608477E3A1}{3CAB88B7-CC3E-46A6-9765-B772AD7761FF})</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Tigrinya (Ethiopia)</td>
<td>ti-ET: Tigrinya Input Method (0473:{E429B25A-E5D3-4D1F-9BE3-0C608477E3A1}{3CAB88B7-CC3E-46A6-9765-B772AD7761FF})</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Turkish - Turkey</td>
<td>tr-TR: Turkish Q (041f:0000041f)</td>
<td></td>
</tr>
<tr class="even">
<td>Turkmen - Turkmenistan</td>
<td>tk-TM: Turkmen (0442:00000442)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Ukrainian - Ukraine</td>
<td>uk-UA: Ukrainian (Enhanced) (0422:00020422)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Upper Sorbian - Germany</td>
<td>hsb-DE: Sorbian Standard (042e:0002042e)</td>
<td></td>
</tr>
<tr class="odd">
<td>Urdu – India</td>
<td>ur-IN: Urdu (0820:00000420)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Urdu (Islamic Republic of Pakistan)</td>
<td>ur-PK: Urdu (0420:00000420)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="odd">
<td>Uyghur - PRC</td>
<td>ug-CN: Uyghur (0480:00010480)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Uzbek - Uzbekistan (Cyrillic)</td>
<td>uz-Cyrl-UZ: Uzbek Cyrillic (0843:00000843)</td>
<td>uz-Latn-UZ: United States - English (0443:00000409)</td>
</tr>
<tr class="odd">
<td>Uzbek - Uzbekistan (Latin)</td>
<td>uz-Latn-UZ: United States - English (0443:00000409)</td>
<td></td>
</tr>
<tr class="even">
<td>Valencian - Valencia</td>
<td>ca-ES-valencia: Spanish (0803:0000040a)</td>
<td></td>
</tr>
<tr class="odd">
<td>Vietnamese - Vietnam</td>
<td>vi-VN: Vietnamese (042a:0000042a)</td>
<td>en-US: United States - English (0409:00000409)</td>
</tr>
<tr class="even">
<td>Welsh - Great Britain</td>
<td>cy-GB: Great Britain Extended (0452:00000452)</td>
<td>en-GB: Great Britain (0809:00000809)</td>
</tr>
<tr class="odd">
<td>Wolof - Senegal</td>
<td>wo-SN: Wolof (0488:00000488)</td>
<td></td>
</tr>
<tr class="even">
<td>Yi - PRC</td>
<td>ii-CN: Yi Input Method(0478:{E429B25A-E5D3-4D1F-9BE3-0C608477E3A1}{409C8376-007B-4357-AE8E-26316EE3FB0D})</td>
<td>zh-CN: Microsoft Pinyin - Simple Fast (0804:{81D4E9C9-1D3B-41BC-9E6C-4B40BF79E35E}{FA550B04-5AD7-411f-A5AC-CA038EC515D7})</td>
</tr>
<tr class="odd">
<td>Yoruba - Nigeria</td>
<td>yo-NG: Yoruba (046a:0000046a)</td>
<td></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[Default Time Zones](default-time-zones.md)

[Add Language Packs to Windows](add-language-packs-to-windows.md)

[Available Language Packs for Windows](available-language-packs-for-windows.md)

[Keyboard identifiers for Windows](windows-language-pack-default-values.md)

[DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md)
