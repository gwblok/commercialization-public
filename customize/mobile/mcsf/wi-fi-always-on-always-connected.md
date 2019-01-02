---
title: Wi-Fi always on, always connected
description: Partners can modify AOAC behavior and UX for non-AOAC mode devices.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 97256af6-ed2d-4869-b7d8-3a7633ed8787


ms.date: 05/02/2017
ms.topic: article


---

# Wi-Fi always on, always connected


Partners can modify AOAC behavior and UX for non-AOAC mode devices.

Partners can use the **LowPowerSupported** and **AlwaysOnAlwaysConnected** settings to modify AOAC behavior and UX. The device’s supported AOAC mode is determined by a combination of the chipset, IHV driver, and the **LowPowerSupported** setting.

-   **LowPowerSupported** – This setting specifies that the IHV driver partially supports AOAC. This setting must only be used if the IHV driver supports a transition from the D0 state to the D2 state and certain low power features.

-   **AlwaysOnAlwaysConnected** – This setting enables partners to specify whether Wi-Fi should remain on when the screen times out. By default, this setting is disabled. Partners should note that this setting does not apply to devices that support partial or full AOAC. In that case, Wi-Fi always remains on and in the lower power state when the screen is idle. Also note that this setting controls the default state of the checkbox **Keep Wi-Fi on when the screen times out** in the **Wi-Fi** &gt; **manage** settings screen. This checkbox is only visible for non-AOAC mode devices.

<a href="" id="constraints---imagetimeonly-for-lowpowersupported"></a>**Constraints:** ImageTimeOnly for LowPowerSupported  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WiFiAOAC"  
                         Description="Use to configure the Wi-Fi driver to support transition from a D0 state to a D2 state and to specify whether
                                      Wi-Fi should stay on when the screen times out."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <!-- This setting is ImageTimeOnly. Specifies if the Wi-Fi driver supports D0 to D2 transitioning. 
             Enable this to indicate 'partial' AOAC state. 
        <Settings Path="WiFi/FirstBoot">  
          <!-- Set to 0 or 'Disabled' (to disable), or set to 1 or 'Enabled' (to enable). -->
          <Setting Name="LowPowerSupported" Value="" />  
        </Settings>  
        -->

        <!-- Configures the Wi-Fi radios to always stay on even after the screen times out. This applies to non-AOAC devices only.
        <Settings Path="WiFi/Config">  
          <!-- Set to 0 or 'Disabled' (to disable), or set to 1 or 'Enabled' (to enable). -->
          <Setting Name="AlwaysOnAlwaysConnected" Value="" />    
        </Settings>  
        -->

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To specify whether the Wi-Fi driver supports transitions from the D0 state to the D2 state and the required low power features, configure the value for `LowPowerSupported` to one of the following values:

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
    <td><p>0 or 'Disabled'</p></td>
    <td><p>IHV driver does not support transitions from the D0 state to the D2 state and the required low power features.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>IHV driver supports transitions from the D0 state to the D2 state and the required low power features.</p></td>
    </tr>
    </tbody>
    </table>

     

4.  To specify whether Wi-Fi should remain on when the screen times out, configure the value for `AlwaysOnAlwaysConnected` to one of the following values:

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
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Disables Wi-Fi from always being on when the screen times out. The <strong>Keep Wi-Fi on when the screen times out</strong> in the <strong>Settings</strong> &gt; <strong>Wi-Fi</strong> &gt; <strong>manage</strong> screen is turned off.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>Enables Wi-Fi to always be on by default when the screen times out. The <strong>Keep Wi-Fi on when the screen times out</strong> in the <strong>Settings</strong> &gt; <strong>Wi-Fi</strong> &gt; <strong>manage</strong> screen is turned on.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device that is connected to a Wi-Fi network.

2.  If your Wi-Fi driver supports a D0 to D2 state transition and you enabled `LowPowerSupported`, verify that the device transitions from a D0 state to a D2 state.

3.  If you have a non-AOAC device and you configured the `AlwaysOnAlwaysConnected` setting, verify whether Wi-Fi remains on when the screen times out. Navigate to the **Wi-Fi** &gt; **manage** settings screen and verify that the **Keep Wi-Fi on when the screen times out** setting is set according to the value that you specified for `AlwaysOnAlwaysConnected`.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
