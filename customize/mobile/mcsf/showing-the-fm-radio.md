---
title: Showing the FM radio
description: For devices that include an FM radio chip, OEMs can show FM Radio in the Apps list.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 824ca9d5-6dda-41a3-83a5-230df3553688


ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/fm-radio
---

# Showing the FM radio


For devices that include an FM radio chip, OEMs can show **FM Radio** in the Apps list. In addition, OEMs can also set the default [FM radio frequency band](fm-radio-frequency-band.md).

By default, the Windows 10 Mobile FM radio UI is hidden.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ShowFMRadioUI"  
                         Description="Use to show the FM radio UI for devices that include an FM radio chip."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="FmRadio">  
          <Setting Name="NotPresent" Value="0" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `NotPresent` to 0 to show the **FM Radio** app.

    **Note**  
    Setting `NotPresent` to 1 is not necessary because the radio UI is hidden by default.

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Verify that **FM radio** is now visible in the Apps list.

## Related topics

[FM radio frequency band](fm-radio-frequency-band.md)

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
