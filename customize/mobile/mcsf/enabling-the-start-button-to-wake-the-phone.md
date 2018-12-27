---
title: Enabling the Start button to wake the phone
description: OEMs can configure the Start button to wake up the phone from the sleep state (also sometimes called the idle state).
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4485fd3f-5ad5-4505-9659-67798e58bf3a


ms.date: 05/02/2017
ms.topic: article


---

# Enabling the Start button to wake the phone


OEMs can configure the Start button to wake up the phone from the sleep state (also sometimes called the idle state). This can be configured on phones with one of the following hardware configurations:

-   The phone has a hardware Start button.

-   The phone uses capacitive buttons, and the buttons share the same touch controller as the display panel but use separate sense lines, or the buttons have a dedicated touch controller. .

**Note**  
Although OEMs typically configure this behavior by adding a registry value in an INF file that is included in a driver package, this behavior can also be configured via the customization process described below. By using both options, OEMs can define the default behavior in the driver for a specific hardware component and modify this behavior as necessary in images for different phone models that use the same driver.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="StartOnIdle"  
                         Description="Use to specify whether the Start button can wake the phone during the idle state."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  

        <Settings Path="Input/Keyboard/EnabledOnIdleButtons">  
          <Setting Name="EnableStartOnIdle" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  For the `EnableStartOnIdle` setting, set the `Value` to one of the following values.

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Value</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>0</p></td>
    <td><p>Prevent the Start button from waking the phone during the idle state. This is also the behavior if you do not define this setting.</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>Enable the Start button to wake the phone during the idle state.</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
