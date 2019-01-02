---
title: Remove cellular functionality from the device
description: If your mobile device does not support a cellular radio or will not be connected to a cellular network, you can remove all cellular-related functionality from the device's user interface by adding the WIFI\_FEATURE\_PACK feature entry in your OEMInput.xml file.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: EBB722FA-F267-49BB-9F4D-DCA6066ECF54


ms.date: 05/02/2017
ms.topic: article


---

# Remove cellular functionality from the device


If your mobile device does not support a cellular radio or will not be connected to a cellular network, you can remove all cellular-related functionality from the device's user interface by adding the WIFI\_FEATURE\_PACK feature entry in your OEMInput.xml file. This feature replaces the WEH\_WIFIONLY feature that you previously used in earlier versions of the mobile OS.

The WIFI\_FEATURE\_PACK package reduces memory usage and improves the user experience by removing the non-functioning cellular-related tiles, icons, and settings. Wi-Fi features will continue to work and airplane mode will also work.

<a href="" id="instructions-"></a>**Instructions:**  
**To create an update package for an existing mobile device using Windows 10 Mobile**

1.  Update your OS image using Windows 10 Mobile as your new base image.

2.  Remove the WEH\_WIFIONLY Microsoft Update package if you are upgrading from Windows Embedded Handheld 8.1.

3.  Add the WIFI\_FEATURE\_PACK as a BSP update.

4.  Test, sign, and submit the update.

**To create a new Windows 10 Mobile image without cellular functionality**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  Add a &lt;Feature&gt;WIFI\_FEATURE\_PACK&lt;/Feature&gt; entry in your OEMInput.xml file.

    ```XML
    <Features>
       <Microsoft>
          <Feature>WIFI_FEATURE_PACK</Feature>
       </Microsoft>
    </Features>
    ```

    For more information about other features you can include in your image, see [Optional features for building images](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/optional-features-for-building-images).

4.  Save the updated OEMInput.xml file and build your mobile OS image.

5.  Verify that the new image doesn't contain cellular-related tiles, icons, and settings. Also verify that Wi-Fi features work and airplane mode functions correctly.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
