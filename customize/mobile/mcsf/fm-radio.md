---
title: Configure the FM radio
description: Devices that support an FM radio can be customized to show the FM radio, and configure the FM radio frequency for specific regions.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 05/02/2017
ms.topic: article


---
# Configure the FM Radio

The BSP provided by the SoC vendor includes support for the FM radio.

Alternative FM radio components that meet the requirements described in the section [2.7: Wireless communications](https://msdn.microsoft.com/en-us/library/windows/hardware/dn756593) of the Chassis Requirements Specification can be used. If alternative components are used, the FM miniport driver can be replaced.

> [!Note]
> If the phone includes an FM radio, it must run the Microsoft-supplied software driver stack, including the port driver.

There are two customization options associated with the FM radio.

* Show the FM radio app to users
* Configure the FM radio frequency for specific regions

Application programming interfaces are not provided for the FM radio.

## Show the FM radio

For devices that include an FM radio chip, OEMs can show **FM Radio** in the Apps list. In addition, OEMs can also set the default [FM radio frequency band](fm-radio-frequency-band.md).

By default, the Windows 10 Mobile FM radio UI is hidden.

<a href="" id="constraints---none"></a>**Constraints:** None

### Instructions

1. Create a customization answer file using the contents shown in the following code sample.

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

2. Specify an `Owner`.
3. Set `NotPresent` to 0 to show the **FM Radio** app.
   > [!Note]
   > Setting `NotPresent` to 1 is not necessary because the radio UI is hidden by default.

### Testing

1. Flash the build containing this customization to a device.
1. Verify that **FM radio** is now visible in the Apps list.

## Configure the FM radio frequency band

OEMs can change the default setting for the FM radio receiver to use an appropriate frequency for the market in which the device will be sold.

> [!Note]
> `NotPresent` must be set to 0 to show the **radio** option in the UI.

**Limitations and restrictions**:

* Additional frequency bands cannot be added to the device.
* The user can change the default setting.

<a href="" id="constraints---none"></a>**Constraints:** None

### Instructions

1. Create a customization answer file using the contents shown in the following code sample.

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

1. Specify an `Owner`.
1. Set `RadioRegion` to specify the default region for the frequency band for the device’s FM radio. Set this to one of the following values:

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

### Testing

1. Flash the build containing this customization to a device.
1. Open the **radio** app.
1. In the radio application, verify that the selected region matches the one you specified in `RadioRegion`. To do this, show the context menu by tapping and holding anywhere on the radio screen. In the context menu, tap **settings** to show the settings page.
1. In the **Settings** page, verify that **Region** is set to the default FM radio region that you selected.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
