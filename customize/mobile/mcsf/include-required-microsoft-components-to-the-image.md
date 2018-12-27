---
title: Include required Microsoft components to the image
description: This customization provides information on how partners can include the required Microsoft components in the OS image.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B1F6D86A-8E5C-4E4F-ABC5-B3DF59916019


ms.date: 05/02/2017
ms.topic: article


---

# Include required Microsoft components to the image


This customization provides information on how partners can include the required Microsoft components in the OS image. For more information about other features you can include or exclude from your image, see [Optional features for building images](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/optional-features-for-building-images).

For a comprehensive list of required Microsoft components that must be included in a Windows 10 Mobile image, refer to the *OEM Policy Document (OPD) for Windows 10 Mobile*.

-   For any phone or other device that is submitted for NAL certification in China (excluding Hong Kong SAR and Macau), partners must meet the following requirements:

    -   Do not include the any Skype app, tile, or functionality as part of any Windows 10 Mobile image, including any test images and final images.

    -   Install the MESSAGINGLITE package, which does not contain Skype, on all devices.

-   For any devices other than those listed above for which MESSAGINGLITE is required, partners must install the MESSAGINGGLOBAL package, which contains Skype.

    **Note**  
    The OS selects the correct messaging package to include as part of the image based on different locale and language combinations and sets this as the default selection. OEMs don't need to select the correct messaging package to install, but should make sure that the correct package is chosen to meet the requirements.

     

<a href="" id="instructions-"></a>**Instructions:**  
**To install the Messaging package that does not include Skype integration**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  Add a &lt;Feature&gt;MESSAGINGLITE&lt;/Feature&gt; entry in your OEMInput.xml file.

    ```
    <Features>
       <Microsoft>
          <Feature>MESSAGINGLITE</Feature>
       </Microsoft>
    </Features>
    ```

4.  Save the updated OEMInput.xml file and rebuild your OS image.

5.  Verify that the Messaging app does not have Skype integration.

**To install the Messaging package that includes Skype integration**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  Add a &lt;Feature&gt;MESSAGINGGLOBAL&lt;/Feature&gt; entry in your OEMInput.xml file.

    ```XML
    <Features>
       <Microsoft>
          <Feature>MESSAGINGGLOBAL</Feature>
       </Microsoft>
    </Features>
    ```

4.  Save the updated OEMInput.xml file and rebuild your OS image.

5.  Verify that the Messaging app includes Skype integration.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
