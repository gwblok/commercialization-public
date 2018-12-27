---
title: Manual network selection timeout
description: OEMs can change the default network selection timeout value.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4ca3a1f4-3bc9-4b3e-b374-f005bb1f0c15


ms.date: 05/02/2017
ms.topic: article


---

# Manual network selection timeout


OEMs can change the default network selection timeout value. By default, the OS allows the device to register on the manually selected network for 60 seconds (or 1 minute) before it switches back to automatic mode.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ManualNetworkSelectionTimeout"  
                         Description="Use to change the default network selection timeout value."  
                         Owner=""  
                         OwnerType="OEM"> 
      
    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/General">  
          <Setting Name="ManualNetworkSelectionTimeout" Value="" />
        </Settings>  
      </Static>

    -->

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `ManualNetworkSelectionTimeout``Value` to a desired timeout value. The range of the value can be from 1-420 seconds. For example, to change the value to 120 seconds (or 2 minutes), you must set the value to 0x78.

    This value is the amount of time that the OS will wait for the modem to register on the manually selected network. If the time lapses and the modem was not able to register on the network that was manually selected by the user, the OS will either:

    -   Switch back to the automatic network selection mode if [Permanent automatic mode](permanent-automatic-mode.md) is enabled and after the user has manually selected a network or the modem was turned on.

    -   Display a dialog that notifies the user that the device was unable to connect to the manually selected network after the device was turned on or after airplane mode was turned off.

<a href="" id="testing-steps-"></a>**Testing steps:**  
**Important**  
To fully test this customization, you must work with your mobile operator partner to perform Steps 2 and 3 in the following procedure.

 

1.  Flash the build that contains this customization to a device that has a UICC.

2.  Ensure that the device is out of range from the home network.

3.  Set the device to the manual network mode by selecting **manual** mode under **Network selection** in the **Settings** &gt; **Cellular & SIM** screen.

4.  While the device attempts to connect to the manually selected network, verify that the OS waits for the amount of time that you specified for `ManualNetworkSelectionTimeout` before it switches back to the automatic network selection mode, or displays a message that indicates that the device was unable to connect to the manually selected network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
