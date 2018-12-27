---
title: Custom user agent string for Microsoft Edge
description: The user agent string indicates which browser you are using, its version number, and details about your system, such as operating system and version.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5ab146be-e7a5-40c5-8dfb-104900a11eba


ms.date: 05/02/2017
ms.topic: article


---

# Custom user agent string for Microsoft Edge


The user agent string indicates which browser you are using, its version number, and details about your system, such as operating system and version. A web server can use this information to provide content that is tailored for your specific browser and phone.

The user agent string for the browser cannot be modified. By default, the string has the following format:

`Mozilla/5.0 (Windows Phone 10.0; Android 4.2.1; <Manufacturer>; <Device>) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/42.0.2311.135 Mobile Safari/537.36 Edge/12.10166`

-   *&lt;Manufacturer&gt;* is automatically replaced with the OEM name. This is the same as the `PhoneManufacturer` setting value that is set as part of the customization [Phone metadata in DeviceTargetingInfo](phone-metadata-in-devicetargetinginfo.md).

-   *&lt;Device&gt;* is replaced with the device name or phone name. This is the same as the `PhoneModelName` setting value that is set as part of the customization [Phone metadata in DeviceTargetingInfo](phone-metadata-in-devicetargetinginfo.md).

**Limitations and restrictions**:

-   The user agent string for the browser cannot be modified outside of the customizations listed above.

-   The user agent type registry setting cannot be modified or used to change the default browser view from Mobile to Desktop.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
