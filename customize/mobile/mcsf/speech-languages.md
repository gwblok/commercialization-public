---
title: Speech languages
description: OEMs can specify the speech languages to include on the mobile device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 973ad41f-622b-4f97-a558-3e0796de4017


ms.date: 05/02/2017
ms.topic: article


---

# Speech languages


OEMs can specify the speech languages to include on the mobile device.

-   The following 7 languages are supported for speech recognition and text-to-speech: en-US, en-GB, zh-CN, de-DE, fr-FR, it-IT, es-ES

    These 7 languages are available on clean installs and can also be downloaded for devices running Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) and Windows 10 Mobile.

-   Additionally, Windows 10 includes 9 more languages for text-to-speech only: es-MX, en-IN, ko-KR, pt-BR, ja-JP, pl-PL, ru-RU, zh-TW, and zh-HK.

    These 9 text-to-speech only languages are available on clean installs only and cannot be downloaded.

Users can install the 7 new speech languages from the **speech** screen in **Settings**, if they are not included on the device by default.

<a href="" id="instructions-"></a>**Instructions:**  
For more information about language customizations, see the overview [Set languages and locales](set-languages-and-locales.md).

To modify the list of speech languages, you must edit the **Speech** section of the OEMInput.xml file before building the device image. You can omit the speech entirely, in which case the user will have to download languages before they can use the speech functionality on the device. To include speech, select one or more of the following options.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Speech language</th>
<th>Value to use in the OEMInput.xml file</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>English (United Kingdom)</p></td>
<td><p>en-GB</p></td>
</tr>
<tr class="even">
<td><p>English (United States)</p></td>
<td><p>en-US</p></td>
</tr>
<tr class="odd">
<td><p>French</p></td>
<td><p>fr-FR</p></td>
</tr>
<tr class="even">
<td><p>German</p></td>
<td><p>de-DE</p></td>
</tr>
<tr class="odd">
<td><p>Italian</p></td>
<td><p>it-IT</p></td>
</tr>
<tr class="even">
<td><p>Spanish (Spain)</p></td>
<td><p>es-ES</p></td>
</tr>
<tr class="odd">
<td><p>Simplified Chinese</p></td>
<td><p>zh-CN</p></td>
</tr>
<tr class="even">
<td><p>English (India) - TTS only</p></td>
<td><p>en-IN</p></td>
</tr>
<tr class="odd">
<td><p>Japanese - TTS only</p></td>
<td><p>ja-JP</p></td>
</tr>
<tr class="even">
<td><p>Korean - TTS only</p></td>
<td><p>ko-KR</p></td>
</tr>
<tr class="odd">
<td><p>Polish - TTS only</p></td>
<td><p>pl-PL</p></td>
</tr>
<tr class="even">
<td><p>Portuguese (Brazil) - TTS only</p></td>
<td><p>pt-BR</p></td>
</tr>
<tr class="odd">
<td><p>Russian - TTS only</p></td>
<td><p>ru-RU</p></td>
</tr>
<tr class="even">
<td><p>Spanish (Mexico) - TTS only</p></td>
<td><p>es-MX</p></td>
</tr>
<tr class="odd">
<td><p>Traditional Chinese (Hong Kong SAR) - TTS only</p></td>
<td><p>zh-HK</p></td>
</tr>
<tr class="even">
<td><p>Traditional Chinese (Taiwan) - TTS only</p></td>
<td><p>zh-TW</p></td>
</tr>
</tbody>
</table>

 

To include one speech language, add one **Language** entry to the **Speech** section of the OEMInput.xml file as shown in the following example:

```
<SupportedLanguages>
  <UserInterface>
    <Language>en-US</Language>
  </UserInterface>
  <Keyboard>
    <Language>en-US</Language>
  </Keyboard>
  <Speech>
    <Language>en-US</Language>
  </Speech>
</SupportedLanguages>
```

To include multiple speech languages, add additional **Language** entries to the **Speech** section of the OEMInput.xml file as shown in the following sample.

```XML
<SupportedLanguages>
  <UserInterface>
    <Language>en-US</Language>
  </UserInterface>
  <Keyboard>
    <Language>en-US</Language>
  </Keyboard>
  <Speech>
    <Language>en-US</Language>
    <Language>pt-BR</Language>
    <Language>ru-RU</Language>
  </Speech>
</SupportedLanguages>
```

<a href="" id="testing-steps-"></a>**Testing Steps:**  
1.  Flash the build containing this customization to a device.

2.  Go to the **speech** screen in **Settings**.

3.  Verify that the list of speech languages installed on the device is correct.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
