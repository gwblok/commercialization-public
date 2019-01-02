---
title: Customizations for contacts
description: Describes the customizations that you can configure for the contacts and contact list on the mobile device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 11/01/2017
ms.topic: article


---
# Customizations for contacts

Describes the customizations that you can configure for the contacts and contact list on the mobile device.

## In this section

| Topic                                 | Description                                                                                   |
|:--------------------------------------|:----------------------------------------------------------------------------------------------|
| [Cortana phone number](cortana-phone-number.md)   | Partners can configure a phone book entry for Cortana to allow users to initiate speech from a car that doesn't have support for activating speech on the device that is connected over Bluetooth.    |
| [Disable wait for phonebook ready signal from the modem](disable-wait-for-phonebook-ready-signal-from-the-modem.md) | FDN SIM contacts syncs from the SIM during device boot. By default, this component waits until the phonebook ready signal is received from the modem and then it verifies whether FDN contact management is enabled on the SIM. If needed, OEMs can disable the wait for the phonebook ready signal.    |
| [Hide contacts without phone numbers](hide-contacts-without-phone-numbers.md)     | Partners can change the default OS behavior so that both contacts with phone numbers and contacts without phone numbers are shown in the People Hub.  |
| [Sort order for contacts](sort-order-for-contacts.md)                 | OEMs can use this customization to set the list of contacts displayed in the People Hub to be organized by last name instead of first name, or first name instead of last name. It is also possible to change the display format of contact names to appear as “First name Last name” or “Last name First name” for markets that use more formal nomenclature.    |
| [Sort order for contacts override](sort-order-for-contacts-override.md)           | OEMs can customize the default values for people sort and display settings as documented in the [Sort order for contacts](sort-order-for-contacts-override.md) customization. However, these settings may be overridden by the defaults for the user’s current locale unless the OEM sets an additional override registry key.        |

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
