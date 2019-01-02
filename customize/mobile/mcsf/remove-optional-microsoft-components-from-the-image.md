---
title: Remove optional Microsoft components from the image
description: This customization provides information on how partners can remove any of the optional Microsoft components.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8b02b8c8-353a-445c-af09-070a4fa8cac4


ms.date: 05/02/2017
ms.topic: article


---

# Remove optional Microsoft components from the image


This customization provides information on how partners can remove any of the optional Microsoft components. For more information about other features you can include or exclude from your image, see [Optional features for building images](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/optional-features-for-building-images).

For a comprehensive list of optional Microsoft components, refer to the *OEM Policy Document (OPD) for Windows 10 Mobile*.

-   Windows 10 Mobile ships with the following optional Microsoft components: Skype Windows Phone Silverlight app, Facebook, MSN Sports, MSN Money, and Continuum.

    An OEM or mobile operator partner may opt-out of installing these optional apps in their final image. Where there is a prepinned Start tile for the replaced optional component, partners must prepin a new Start tile in its place using one of the other Microsoft apps that OEMs can prepin to Start. Partners are encouraged to ship these components as part of their final OS image except in markets where these applications are not allowed.

-   For any phone or other device that is intended to be sold in China, partners must not include any Facebook app or tile provided by Microsoft as part of any Windows 10 Mobile image, including any test images and final images.

<a href="" id="instructions-"></a>**Instructions:**  
**To remove Skype Windows Phone Silverlight app from the OS image**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  If SKYPE is in the list of optional Microsoft features, delete the **Feature** entry from the list.

    In the following example, the &lt;FEATURE&gt; entry shows what you need to delete from your OEMInput.xml file.

    ```XML
    <Features>
       <Microsoft>
          <Feature>SKYPE</Feature>
       </Microsoft>
    </Features>
    ```

4.  Save the updated OEMInput.xml file and rebuild your OS image.

5.  Verify that the Skype Windows Phone Silverlight app is no longer part of the OS image.

**To remove Facebook from the OS image and Start screen**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  If FACEBOOK is in the list of optional Microsoft features, delete the **Feature** entry from the list.

    In the following example, the &lt;FEATURE&gt; entry shows what you need to delete from your OEMInput.xml file.

    ```
    <Features>
       <Microsoft>
          <Feature>FACEBOOK</Feature>
       </Microsoft>
    </Features>
    ```

4.  Save the updated OEMInput.xml file and rebuild your OS image.

5.  Verify that Facebook is no longer part of the OS image and does not appear in the Start screen.

    For partners that opt-out of Facebook, partners must prepin a new Start tile in its place using one of the other Microsoft components that OEMs can prepin to Start.

**To remove Continuum from the OS image**

1.  Locate the OEMInput.xml file that you are using to define your image.

2.  Find the **Features** section, and within the **Microsoft** child element, review the **Feature** elements.

3.  If Docking is in the list of optional Microsoft features, delete the **Feature** entry from the list.

    In the following example, the &lt;FEATURE&gt; entry shows what you need to delete from your OEMInput.xml file.

    ```XML
    <Features>
       <Microsoft>
          <Feature>Docking</Feature>
       </Microsoft>
    </Features>
    ```

4.  Save the updated OEMInput.xml file and rebuild your OS image.

5.  Verify that Continuum is no longer part of the OS image.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
