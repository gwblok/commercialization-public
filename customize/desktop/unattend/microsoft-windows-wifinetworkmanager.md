---
title: Microsoft-Windows-WiFiNetworkManager
description: Specifies settings that you can configure for the Wi-Fi Sense feature.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: C13C9E90-E50B-4AD8-AA86-1AA10CDDD218
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-WiFiNetworkManager

> [!Important]
> **This setting has been deprecated**. The information about this deprecated setting is provided for reference only. The Wi-Fi Sense credential sharing feature has been removed.

Specifies settings that you can configure for the Wi-Fi Sense feature.

Wi-Fi Sense automatically connects you to Wi-Fi so you can get online quickly in more places. It can connect you to open Wi-Fi hotspots that it knows about through crowdsourcing, or to Wi-Fi networks that your contacts have shared with you by using Wi-Fi Sense.

Wi-Fi Sense can discover your device location even when location is turned off for your user account. This is true whenever Wi-Fi Sense is turned on. Wi-Fi Sense uses your location to find suggested open Wi-Fi hotspots.

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DefaultAutoConnectSharedState](microsoft-windows-wifinetworkmanager-defaultautoconnectsharedstate.md) | If enabled, the OOBE <strong>Wi-Fi Sense</strong> checkbox to share networks with contacts will be checked. |
| [WiFiSharingFacebookInitial](microsoft-windows-wifinetworkmanager-wifisharingfacebookinitial.md) | Controls how Wi-Fi networks are shared with the user's Facebook contacts. |
| [WiFiSharingOutlookInitial](microsoft-windows-wifinetworkmanager-wifisharingoutlookinitial.md) | Controls how Wi-Fi networks are shared with the user's Outlook contacts. |
| [WiFiSharingSkypeInitial](microsoft-windows-wifinetworkmanager-wifisharingskypeinitial.md) | Controls how Wi-Fi networks are shared with the user's Skype contacts. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
