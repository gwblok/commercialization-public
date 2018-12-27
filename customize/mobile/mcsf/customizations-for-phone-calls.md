---
title: Customizations for phone calls
description: Provides information about customizations you can configure for the phone or dialer app including branding, visual voicemail, caller ID matching, dialer codes, and more.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 78f699de-5dd9-4f87-8598-9a2242b9a5f3


ms.date: 05/02/2017
ms.topic: article


---
# Customizations for phone calls

Provides information about customizations you can configure for the phone or dialer app including branding, visual voicemail, caller ID matching, dialer codes, and more.

## In this section

| Topic                                 | Description                                                                                   |
|:--------------------------------------|:----------------------------------------------------------------------------------------------|
| [Adjust the call duration information for CDMA calls](adjust-the-call-duration-information-for-cdma-calls.md) | On CDMA devices, call durations in the call history may include the time spent before the call was connected. This behavior results in an incorrect calculation of the call duration. OEMs can address this potential issue by enabling this customization, which excludes the time spent before the call was connected. When enabled, the customization will also adjust the call duration to indicate that zero time was spent if the call ends before the connection was made. |
| [Always display the dialed phone number](always-display-the-dialed-phone-number.md)   | OEMs can change the default behavior so that the number that's displayed in the call screen always matches the dialed phone number even if the number that the call connected to may be different.    |
| [Branding for phone calls](branding-for-phone-calls.md)   | Partners can add a custom image that displays the mobile operator name or logo on the **Incoming call** screen.  |
|[Caller ID matching](caller-id-matching.md)    | Mobile operators can modify the default mapping values specified by Microsoft using the settings in the `Phone/CallIDMatchOverrides`settings group. If mobile operators specify a number of digits that is outside the OS-supported range of 4-20, the OS defaults back to 6 digits. For any country/region that doesn't exist in the default mapping table, mobile operators can use the legacy `CallIDMatch` setting to specify the minimum number of digits to use for matching caller ID. |
| [Cause codes](cause-codes.md) | On GSM networks, OEMs can enable mobile operator-defined codes, or cause codes, to show in the UI whenever a phone call is terminated unexpectedly.   |
| [Conditional call forwarding](conditional-call-forwarding.md) | Partners can now show the call forwarding icon for conditional call forwarding as well as unconditional call forwarding.  |
| [Configure DTMF tones](dtmf-tones.md) | Partners can configure DTMF tone settings when VoLTE calls are supported.  |
| [Configure message waiting indicator notifications](configure-message-waiting-indicator-notifications.md) | Depending on the scenario that partners want to support, partners can configure the voicemail system so the device either ignores or responds to message waiting indicator (MWI) notifications.   |
| [Dialer codes for supplementary services](dialer-codes-for-supplementary-services.md) | Partners can define a dialer code to use for services like changing the pin, changing the password, caller ID, call forwarding, call waiting, call blocking, and so on.   |
| [Dialer codes to launch diagnostic applications](dialer-codes-to-launch-diagnostic-applications.md)   | To use an OEM diagnostic app in environments such as a service center, OEMs can configure special dialer codes to start the application. OEMs can also configure dialer codes to start apps to interact with mobile operator networks or to diagnose phone malfunctions.  |
| [Dial string overrides when roaming](dial-string-overrides-when-roaming.md)   | Partners can map certain dial strings to corresponding override numbers that are dialed when the user is roaming. To the user, it will appear as if the original number was dialed.   |
| [Disable link to contact card in active call screen](disable-link-to-contact-card-in-active-call-screen.md)   | Disable the ability to access a contact's information while in the active call screen.        |
| [Disable video upgrade Store navigation](disable-video-upgrade-store-navigation.md)   | Disable automatic navigation to the Microsoft Store when the user attempts a video upgrade during a phone call, for which there is no installed app.  |
| [Disable voicemail phone number display](disable-voicemail-phone-number-display.md)   | Disable voicemail phone number display on the call progress screen.   |
| [Dismiss the last USSD waiting dialog](dismiss-the-last-ussd-waiting-dialog.md)   | Dismiss the last USSD waiting dialog in the case where there is a sequence of USSD or SIM app dialogs.    |
| [Emergency phone numbers](emergency-phone-numbers.md) | Partners can edit the list of valid emergency phone numbers for the market in which the phone will be sold.   |
| [Enable call recording by default](enable-call-recording-by-default.md)  | Partners can configure devices to have the call recording feature enabled by default. |
| [Enable IMS services](enable-ims-services.md) | Partners can identify which IP Multimedia Subsystem (IMS) services, if any, are enabled on the device by default. The IMS services that can be identified are: IMS, SMs over IMS, Voice over IMS, and Video over IMS. |
| [Enable RCS](enable-rcs.md)   | OEMs can configure the RCS settings using the multivariant support in the OS. Using these settings, you can specify whether the device is RCS-enabled,specify whether to use single registration for RCS, and configure the user experience for RCS. |
| [Hide call forwarding](call-forwarding.md) | Partners can hide the user option for call forwarding.    |
| [Maximum number of participants in a VoLTE conference call](maximum-number-of-participants-in-a-volte-conference-call.md) | OEMs can specify the maximum number of participants or callers that can be added to a voice over LTE (VoLTE) conference call based on the mobile operator's network requirements. |
| [Network-controlled caller ID settings](network-controlled-caller-id-settings.md) | For markets or mobile operators that require support for network-controlled settings for outgoing caller ID, OEMs can configure the setting to indicate whether the network default setting is allowed and specify the default initial value for the caller ID setting.   |
| [Override the voicemail number on the UICC](overriding-the-voicemail-number-on-the-uicc.md)   | Mobile operators can override the voicemail number on the UICC with a different voicemail number that is configured in the registry.  |
| [Supplementary services exclusions](supplementary-services-exclusions.md) | Partners can define a dialer code to use for 3GP USSD services like changing the pin, changing the password, caller ID, call forwarding, call waiting, call barring, and so on. Partners can define new mappings or disable the default mappings. To define a new mapping or change the behavior of a provided supplementary service mappings, see [Dialer codes for supplementary services](dialer-codes-for-supplementary-services.md)  |
| [Trim supplementary service codes](phone-settings--trim-supplementary-service-codes.md)| OEMs can trim supplementary service codes to ensure network compatibility. When a code is sent using a USSD string in a ##code# format, `EnableSupplementaryServiceEraseToDeactivateOverride` trims the USSD string so #code# is sent. This customization applies only to codes that use the ##code# format.  |
| [Use OK for USSD dialogs](use-ok-for-ussd-dialogs.md) | To meet certain market requirements or user expectations, OEMs can change the button label in USSD dialogs from **Close** (the default) to **OK**.    |
| [Use HD audio codec for call branding](use-hd-audio-codec-for-call-branding.md)   | OEMs can customize call progress branding when a call is made using a specific audio codec.   |
| [Use voice domain for emergency call branding](use-voice-domain-for-emergency-call-branding.md)   | To meet mobile operator requirements, OEMs can enable the voice domain to decide whether to use **Emergency calls only** or **No service** in the phone UI branding.    |
| [Visual voicemail](visual-voicemail.md)   | Visual voicemail supports both traditional voicemail (retrieved through a phone call) and visual voicemail. Users can select between traditional voicemail and visual voicemail when they first attempt to access voicemail. If the mobile operator does not support this visual voicemail implementation, the user will only see the traditional voicemail option. For mobile operators that have their own particular brand that they want to use instead of visual voicemail, partners can rebrand all instances of **Visual voicemail** in the Windows 10 Mobile UI to use the operator's brand. |
| [Voice over LTE call indication](voice-over-lte-call-indication.md)   | Partners can add a string to the phone's call progress screen to indicate if the active call is a voice over LTE (VoLTE) call depending on whether the phone call is in high quality voice status such as when using AMR-WB codec.    |
| [Voicemail number for CDMA phones](voicemail-number-for-cdma-phones.md)   | CDMA mobile operator partners who do not have the voicemail numbers on the device SIM can configure the voicemail number for their devices.   |

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
