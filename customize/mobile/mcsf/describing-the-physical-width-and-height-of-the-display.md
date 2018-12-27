---
title: Describing the physical width and height of the display
description: As part of implementing support for the touch controller hardware, OEMs must add registry values that specify the physical width and height the portion of the screen that is used to render the mobile device UI.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 10455208-3c90-4be3-b805-e1ef03c93a73


ms.date: 05/02/2017
ms.topic: article


---

# Describing the physical width and height of the display


As part of implementing support for the touch controller hardware, OEMs must add registry values that specify the physical width and height the portion of the screen that is used to render the mobile device UI. The OS uses this information to properly scale touch gestures and help ensure a fluid user experience.

**Note**  
Although OEMs typically configure this behavior by adding a registry value in an INF file that is included in a driver package, this behavior can also be configured via the customization process described below. By using both options, OEMs can define the default behavior in the driver for a specific hardware component, and modify this behavior as necessary in images for different device models that use the same driver.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisplayWidthAndHeight"  
                         Description="Use to specify the physical width and height the portion of the screen that is used to render the phone UI."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  

        <Settings Path="Input/Touch/DisplayProperties">  

          <!-- The following values are in 10's of micrometers. -->
          <Setting Name="DisplayHeight" Value="" />   
          <Setting Name="DisplayWidth" Value="" />   

        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  For the `DisplayHeight` setting, set the `Value` to the height of the display in 10's of micrometers, formatted as a hexadecimal value. For example, `Value="0x206C"` specifies a height of 83 mm.

4.  For the `DisplayWidth` setting, set the `Value` to the width of the display in 10's of micrometers, formatted as a hexadecimal value. For example, `Value="0x1388"` specifies a width of 50 mm.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
