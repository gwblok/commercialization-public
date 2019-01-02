---
title: FM radio frequency band
description: OEMs can change the default setting for the FM radio receiver to use an appropriate frequency for the market in which the device will be sold.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 25166bab-307f-4207-9901-1300d8fbed09


ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/fm-radio
---

# FM radio frequency band


OEMs can change the default setting for the FM radio receiver to use an appropriate frequency for the market in which the device will be sold.

**Limitations and restrictions**:

-   Additional frequency bands cannot be added to the device.

-   The user can change the default setting.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="FMRadioRegion"  
                         Description="Use to change the default frequency band for the FM radio receiver."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="FmRadio">  
          <Setting Name="NotPresent" Value="0" />
          <Setting Name="RadioRegion" Value="" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Make sure that `NotPresent` is set to 0 to show the **radio** option in the UI. For more information, see [Showing the FM radio](showing-the-fm-radio.md).

4.  Set `RadioRegion` to specify the default region for the frequency band for the device’s FM radio. Set this to one of the following values:

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
    <td><p>1</p></td>
    <td><p>North America</p></td>
    </tr>
    <tr class="even">
    <td><p>2</p></td>
    <td><p>World</p></td>
    </tr>
    <tr class="odd">
    <td><p>3</p></td>
    <td><p>Japan</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Open the **radio** app.

3.  In the radio application, verify that the selected region matches the one you specified in `RadioRegion`. To do this, show the context menu by tapping and holding anywhere on the radio screen. In the context menu, tap **settings** to show the settings page.

4.  In the **Settings** page, verify that **Region** is set to the default FM radio region that you selected.

## Related topics

[Showing the FM radio](showing-the-fm-radio.md)

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
