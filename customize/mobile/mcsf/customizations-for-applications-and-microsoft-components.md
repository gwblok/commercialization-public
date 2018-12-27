---
title: Customizations for applications and Microsoft components
description: This section contains information about customizations related to apps and Microsoft components.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0ec3de7c-f796-4c48-af57-8e73a87af3e5


ms.date: 05/02/2017
ms.topic: article


---
# Customizations for applications and Microsoft components

This section contains information about customizations related to apps and Microsoft components.

## In this section

| Topic                                 | Description                                                                                   |
|:--------------------------------------|:----------------------------------------------------------------------------------------------|
| [Active phone cover settings](active-phone-cover-settings.md) | OEMs can create and register an active phone cover app, which allows partners to create a user experience with their mobile device cover accessories. This app must be preloaded on the phone as a Settings/CPL application.  |
| [Customize the SIM toolkit](customize-the-sim-toolkit.md) | OEMs can change the display duration for certain SIM toolkit UI dialogs or messages if the default values do not meet the requirements of the mobile operator.    |
| [Enhanced apps experience for medium and large screens](enhanced-apps-experience-for-medium-and-large-screens.md) | OEMs can use the `UserPreferenceWidth` setting to override the default behavior based on the screen size and specify the physical width of the device (instead of using the automatically calculated `HORZSIZE` value). |
| [Include required Microsoft components to the image](include-required-microsoft-components-to-the-image.md)   | This customization provides information on how partners can include the required Microsoft components in the OS image.    |
| [Phone calls/SMS filter applications](phone-callsms-filter-applications.md)   | OEMs can build and register a phone call/SMS filter application, which helps reduce the number of unwanted phone calls and text messages that users receive.  |
| [Preload an app with a dependency](preload-an-app-with-a-dependency.md)   | To preinstall an app that has dependencies on other packages or components, you must ensure the dependencies are preinstalled first, before your app. If the dependent packages or components are not installed first, your app preinstall will fail.   |
| [Remove optional Microsoft components from the image](remove-optional-microsoft-components-from-the-image.md) | This customization provides information on how partners can remove any of the optional Microsoft components.  |
| [Store live tile](store-live-tile.md) | The Store tile, when medium-sized, becomes a live tile. It shows both the Microsoft Store logo and the name. The Microsoft Store live tile cycles through apps that the user will see in the Store and lets the user discover apps outside of the Store. Microsoft recommends that partners keep the default Store live tile behavior. However, partners may change the default behavior to turn off the Store live tile and to prevent the OS from using cellular data to update the Store live tile in the background.  |

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
