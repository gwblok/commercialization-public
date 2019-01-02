---
title: Customizations for cellular connectivity
description: Describes the customizations for configuring cellular connectivity settings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2302cb01-7ccd-4840-8559-f1ac81f28082


ms.date: 05/02/2017
ms.topic: article


---
# Customizations for cellular connectivity

Describes the customizations for configuring connectivity settings.

## In this section

| Topic                                 | Description                                                                                   |
|:--------------------------------------|:----------------------------------------------------------------------------------------------|
| [Background cellular data restriction](background-cellular-data-restriction.md)   | To meet market or mobile operator requirements, OEMs can restrict background data in the data usage settings. |
| [Cellular data connection icon](cellular-data-connection-icon.md) | The one-, two-, or three-character codes used to signify the data connection type in the status bar can be modified.  |
| [Custom percentages for signal strength bars](custom-percentages-for-signal-strength-bars.md) | Partners must modify the percentage values used for the signal strength bars in the status bar.   |
| [Data transfer indicator](data-transfer-indicator.md)     | OEMs can display a data transfer indicator on a device’s status bar for mobile operators that require it. |
| [Default highest connection speed](default-highest-connection-speed.md)   | Partners can set the default value for the Highest connection speed option in the Settings > Cellular & SIM > SIM screen by specifying the bitmask for any combination of radio technology to be excluded from the default value. The connection speed that has not been excluded will show up as the highest connection speed.   |
| [Default roaming option](default-roaming-option.md)   | Partners can set the default value for the Default roaming options option in the Cellular & SIM settings screen.  |
| [Disable Cell Broadcast](disable-cell-broadcast.md)   | By default, Cell Broadcast (also known as Short Message Service-Cell Broadcast (SMS-CB)) is a feature that is active at all times.    |
| [Extended error messages for reject codes](extended-error-messages-for-reject-codes.md)   | When a reject code is sent by the network, partners can specify that extended error messages should be displayed instead of the standard simple error messages. This customization is intended for use only when required by the mobile operator’s network.   |
| [Hide CDMA mode selection](hide-cdma-mode-selection.md)   | For CDMA phones, partners can hide CDMA option in the network Mode selection drop-down that appears on the Cellular & SIM screen in Settings. |
| [Hide Cellular & SIM Settings](cellular-settings-for-phones.md)   | OEMs can hide certain user options for phones that appear in the Cellular & SIM screen in Settings. These options include: Network Mode selection drop-down for World mode, Network Selection drop-down for GSM, and Network Type drop-down for CDMA. |
| [LTE attach: GUID for user configured internet APN](lte-attach-guid-for-user-configured-internet-apn.md)  | Partners can set the OEMConnectionId that is used when creating the user-configured connection for internet from the SIM settings screen. |
| [LTE attach: Mapping OEMConnectionId values to modem profiles](lte-attach-mapping-oemconnectionid-values-to-modem-profiles.md)    | Partners can set the list of OEMConnectionId values that map to an LTE attach profile in the mobile broadband driver. |
| [Manual network selection timeout](manual-network-selection-timeout.md)   | OEMs can change the default network selection timeout value. By default, the OS allows the device to register on the manually selected network for 60 seconds (or 1 minute) before it switches back to automatic mode.    |
| [Maximum number of PDP contexts](maximum-number-of-pdp-contexts.md)   | OEMs can set different maximum values for the number of PDP contexts for the device if required by their mobile operator. |
| [Permanent automatic mode](permanent-automatic-mode.md)   | OEMs can enable permanent automatic mode for mobile networks that require the cellular settings to revert to automatic network selection after the user has manually selected another network when roaming or out of range of the home network.   |
| [Preferred data provider list](preferred-data-provider-list.md)   | For mobile operators that require it, OEMs can set a list of MCC/MNC pairs for the purchase order (PO) carrier or primary operator so that it can be set as the default data line for phones that have a dual SIM.    |
| [Roaming filter](roaming-filter.md)   | Partners can add roaming filters that determine when the device appears to be roaming, based on the network the device is currently connected to. With roaming filters enabled, connections on other companies’ specified networks are not treated as roaming.    |

## Related topics

[Customizations for Wi-Fi settings and Connectivity](customizations-for-wifi-settings.md)

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
