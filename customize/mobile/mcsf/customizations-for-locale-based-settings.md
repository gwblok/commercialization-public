---
title: Customizations for locale-based settings
description: Describes the customizations that you can configure to optimize mobile devices for different regions they may ship to. Includes topics on shipping mobile devices to Chines.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 11/01/2017
ms.topic: article


---
# Customizations for locale-based settings

Describes the customizations that you can configure to optimize mobile devices for different regions they may ship to. Includes topics on shipping mobile devices to Chines.

## In this section

| Topic                                 | Description                                                                                   |
|:--------------------------------------|:----------------------------------------------------------------------------------------------|
| [Assistance for dialing international phone numbers](assistance-for-dialing-international-phone-numbers.md)   | Partners can turn off the international assist feature that helps users with the country codes needed for dialing international phone numbers.    |
| [China Type Approval requirement: app install prompts](cta-app-install-prompts.md) | To meet China Type Approval (CTA) requirements for devices shipping in China, OEMs must show a notification dialog to alert users when the app being downloaded does certain things. |
| [Contact management on the SIM (CN only)](contact-management-on-the-sim.md)        | Partners can specify that users should be able to read, edit, delete, import, and export contact information on their SIM (basic SIM, USIM, or RUIM). This customization is only available for devices sold in China.    |
| [Disable NITZ or daylight saving time](disabling-nitz-or-daylight-saving-time.md)  | OEMs can configure Network Identity and Time Zone (NITZ) to handle daylight saving time appropriately for their market, or disable automatic setting of date and time completely. |
| [Display location icon](display-location-icon.md)                                  | Partners can hide the location icon in the system tray if they choose.   |
| [Ignore NITZ information from LTE networks](ignore-nitz-information-from-lte-networks.md) | For mobile networks that can receive Network Identity and Time Zone (NITZ) information from multiple sources, partners can set the device to ignore the time received from an LTE network.    |
| [Microsoft Store for China](windows-phone-store-for-china.md)                      | For a Windows 10 Mobile device shipping in China, OEMs must specify that the device is intended for that market by setting the PhoneROMLanguage setting in DeviceTargetingInfo to the appropriate locale ID. |
| [Mobile device languages](phone-languages.md)                                      | Partners must select the set of available languages to include on the mobile device. Partners must also specify one of the included languages as the default device language.    |
| [Network Time Protocol support](network-time-protocol-support.md) | Use to automatically set the time using an NTP client in a mobile device that doesn't support NITZ, or when cellular data is not available.   |
| [Regional format](regional-format.md)                                              | Partners can specify the default country/region, regional format, pre-enabled keyboard, and speech languages for the device.                                       |
| [Speech languages](speech-languages.md)                                            | OEMs can specify the speech languages to include on the mobile device.   |
| [Default list of countries/regions](default-list-of-countries-regions.md)          | OEMs can select the countries/regions to exclude from the default list shown in the mobile device's Country/Region list in the Settings screen.                      |
| [Preferred system types for phone connectivity (CN only)](preferred-system-types-for-phone-connectivity.md)   | OEMs can provide more control over the system types that their devices use to connect. This customization is only for China. OEMs should not set this customization unless required by the mobile operator.   |
[Threshold for automatic time update](threshold-for-automatic-time-update.md)   | For mobile networks that support Network Identity and Time Zone (NITZ), OEMs can specify the difference (in number of seconds) between the NITZ information and the current device time before a device time update is triggered. |
| [Time zone priority list](time-zone-priority-list.md)                              | Beginning with Windows 10 Mobile, this customization is no longer necessary as the OS supports a location-based timezone detection service. However, to maintain backwards compatibility for some RPAL APIs that were previously released, an updated table of the timezone IDs is provided for your reference.    |
| [WAP browser support (CN and IN only)](wap-browser-support.md) | For phones that will ship in China and India, OEMs can add one preloaded WAP browser to the phone, which will automatically be launched when the user tries to open a WAP link. The WAP browser must be written as an application, and must go through the standard Microsoft Store submission process.   |

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
