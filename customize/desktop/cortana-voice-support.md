---
title: Cortana voice support
description: How Cortana voice supports customers during OOBE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 09/27/2017
ms.topic: article


---
# Cortana voice support

Cortana voice walks the user through the OOBE experience, enabling the user to complete parts of OOBE by responding to spoken prompts. Cortana voice during OOBE is currently available in the following languages: **en-US**, **es-MX**, **ja-JP**, **en-GB**, **fr-FR**, **it-IT**, **de-DE**, **es-ES**, **fr-CA**, **en-CA**, **en-AU**, **pt-BR**, **zh-CN**.

The `language` value you set in OOBE.xml impacts the voice used during OOBE. The OOBE.xml value for `language` must be a language/region decimal ID associated with a Windows language pack. For example, the **English (United States)** language pack has an associated language/region decimal ID of **1033**. For a full list of language/region decimal IDs that you can set in OOBE.xml, see [Available Language Packs for Windows](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/available-language-packs-for-windows).

Cortana voice is enabled after the customer selects a language from the Language selection screen in OOBE. If the language selected by the customer, combined with the `language` in OOBE.xml, is supported by Cortana, Cortana will assist in that language upon entering the Region selection page.

Cortana voice will continue to assist throughout the OOBE process in that same supported language. Even if the user selects a region on the Region page that is not supported by Cortana, or selects a region that would cause Cortana to use a different accent after OOBE, Cortana voice will not change during OOBE.

If the language selected by the customer on the Language page combined with the `language` in OOBE.xml is not one of the supported combinations for Cortana, then the OOBE experience will be silent.

After the user completes OOBE, the voice used in the Cortana app will be based on the Language and Region selected during OOBE. At that point, Cortana will no longer consider the language in OOBE.xml.

Here are a few examples:

| Language selected by customer (during OOBE) | Language set in OOBE.xml | Region selected by customer (during OOBE) | Cortana voice assistance result (during OOBE) | Cortana app voice result (after OOBE) |
|:------------------|:------------------|:------------------|:------------------|:------------------|
| English           | 1033 (en-US language pack)  | 244 (US)  | en-US     | en-US         |
| English           | 2057 (en-GB language pack)  | 244 (US) | en-GB     | en-US         |
| Russian           | 1049 (ru-RU language pack)  | 203 (RU) | Silent    | Not supported |

## Disable Cortana voice support

For testing purposes, you can turn Cortana voice off, but you must enable it again before the device ships. To temporarily turn Cortana voice off, set the following registry key.

`HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE : DisableVoice = 1 (DWORD)`

> [!Note]
> This setting should only be disabled for testing purposes. Shipping a device with Cortana voice support disabled is an unsupported configuration.

## “Hey Cortana” feature

The “Hey Cortana” feature enables users to more easily engage Cortana on their Windows 10 device by speaking the phrase “Hey Cortana”. 

For devices that meet hardware requirements, users have the option of enabling "Hey Cortana" during the OOBE flow, on the screen which asks the user if they’d like to make Cortana their personal assistant. The option is unchecked by default.

 After OOBE, users can also enable "Hey Cortana" from **Cortana & Search Settings**. By default, "Hey Cortana" is not enabled.

## Configure Hey Cortana 

To optimize battery life, by default, Windows only asks users if they want to enable "Hey Cortana" on desktop devices with a microphone

For Windows 10, version 1709 and later, you an also include this option during OOBE if your device meets the policy requirement of including a [hardware-offloaded key spotter (HW KWS)](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).

For devices that meet this requirement, set the registry key: 

`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech_OneCore\AudioPolicy : VoiceActivationIsBatteryCertified` = 1.

To learn more, see [Voice Activation](https://docs.microsoft.com/windows-hardware/drivers/audio/voice-activation).
