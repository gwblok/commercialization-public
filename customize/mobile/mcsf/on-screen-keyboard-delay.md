---
title: On-screen keyboard delay
description: When an external keyboard (e.g. Bluetooth keyboard or barcode scanner which connects as HID keyboard) is used with a device, the on-screen keyboard is hidden. When the screen is touched, there is a hard-coded delay of 60 seconds before the on-screen keyboard reappears. This setting enables you to change that delay.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 16bffab4-8ac1-4bd9-93cf-bbe34810bf3b


ms.date: 05/02/2017
ms.topic: article


---
# On-screen keyboard delay

When an external keyboard (e.g. Bluetooth keyboard or barcode scanner which connects as an HID keyboard) is used with a device, the on-screen keyboard is hidden. When the screen is touched, there is a hard-coded delay period of 60 seconds before the on-screen keyboard reappears. Typically, the user selects an input field on the screen and then uses the external keyboard/barcode scanner to enter the data.

This customization enables an OEM to change that delay period. The delay value is read on boot-up and cannot be changed during runtime. The optional customization specifies the delay in seconds with a default value of 60. If the value is set to 0, then the on-screen keyboard is not hidden.

**Constraints:** ImageTimeOnly

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
        Name="HWKeyboardActivityInterval"
        Description="Use to configure the setting for the delay in showing the on-screen keyboard when an external keyboard is connected"
        Owner=""
        OwnerType="OEM">
        <Static>
            <Settings>
                <Setting Name="HWKeyboardActivityInterval" Value="" />
                <RegistrySource Type="REG_DWORD" Path="HKEY_LOCAL_MACHINE\Software\Microsoft\Input\HWKeyboardActivityInterval" />
            </Settings>
        </Static>
   </ImageCustomizations>
   ```

1. Specify an Owner.
1. Set the value to the required delay between when a user touches the screen of the device, and when the on-screen keyboard appears, in seconds.

## Testing steps

1. Flash the build containing this customization to a device
1. Connect an external Bluetooth keyboard to the device
1. Select the input field on the screen via the on-screen keyboard
   1. Type **abc** via the on-screen keyboard.
   1. Type **dce** via the external keyboard. The on-screen keyboard shrinks from the screen.
   1. Touch the screen again and confirm the on-screen keyboard remains hidden until the specified delay expires.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
