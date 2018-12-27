---
title: Warning about light theme for AMOLED and OLED screens
description: OEMs can choose to display a warning about battery life if the user selects the light theme on phones with AMOLED or OLED displays.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ee78d8e1-adc0-4f19-9491-c6ecc1f0490b


ms.date: 05/02/2017
ms.topic: article


---

# Warning about light theme for AMOLED and OLED screens


OEMs can choose to display a warning about battery life if the user selects the light theme on phones with AMOLED or OLED displays. This customization is not relevant for other screen types, as there is not a significant power difference between the themes with the light and dark background.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="OLEDWarning"  
                         Description="Use to display the battery life warning on phones with AMOLED or OLED displays."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Theme">  
          <Setting Name="OLEDWarning" Value="1" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Do not modify the `Value`.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image containing this customization to a phone.

2.  Go to the **Colors** settings screen.

3.  Set the **Choose your mode** option to **Light**.

4.  Verify that the warning text appears above the mode option.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
