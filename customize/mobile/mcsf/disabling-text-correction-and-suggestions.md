---
title: Disable text correction and suggestions
description: For markets that do not use any of the available input languages, partners pick an alternative available input language as the default, but disable text prediction, auto-correction, and the spelling checker by default, using this customization.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 16bffab4-8ac1-4bd9-93cf-bbe34810bf3b


ms.date: 05/02/2017
ms.topic: article


---

# Disable text correction and suggestions


For markets that do not use any of the available input languages, partners pick an alternative available input language as the default, but disable text prediction, auto-correction, and the spelling checker by default, using this customization.

Partners must not remove any keyboards, disable default keyboards for an input language, nor modify any keyboard layouts in any way. However, for markets that do not use any of the available input languages, partners pick an alternative available input language as the default, but disable text prediction, auto-correction, and the spelling checker. This prevents the user’s words from being automatically changed to similar words in the alternate language as they type.

Users can turn text prediction, auto-correction, and the spelling checker back on by going to the **keyboard** screen in **Settings**, tapping their desired keyboard language, and selecting **Suggest text**.

**Limitations and restrictions:**

-   Partners can disable text correction and suggestions for only one language. This functionality cannot be disabled for Japanese, Chinese, or Korean.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisableTextCorrection"  
                         Description="Use to disable text prediction, auto-correction, and spelling checker for an alternative input language."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="TextInput/Intelligence">  
          <Setting Name="DisablePredictions" Value="" />       
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value` to the locale or alternative input language that must have the text intelligence features disabled. For example, to disable text correction and suggestions for English (UK), set `Value` to `en-gb`.

<a href="" id="testing-steps-"></a>**Testing Steps:**  
1.  Flash the build containing this customization to a device.

2.  Go to the **keyboard** screen in **Settings**.

3.  Choose the keyboard language where you turned off text correction and suggestions to open the keyboard settings.

4.  Verify that the checkboxes for **Suggest text**, **Highlight misspelled words**, **Correct misspelled words**, and **Insert a space after selection a suggestion** are unchecked.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
