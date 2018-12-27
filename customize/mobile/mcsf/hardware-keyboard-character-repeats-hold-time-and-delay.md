---
title: Hardware keyboard character repeats hold time and delay
description: For devices that have a hardware keyboard, partners can optionally set the character repeat hold time and delay.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ca578835-2c73-4aa9-865f-d8ed51c62b1c


ms.date: 05/02/2017
ms.topic: article


---

# Hardware keyboard character repeats hold time and delay


For devices that have a hardware keyboard, partners can optionally set the character repeat hold time and delay.

The optional keyboard customizations are:

-   The amount of time, in milliseconds, the user must hold down a key before the keyboard character repeats.

-   The amount of time, in milliseconds, to use as the delay between each keyboard character repeats.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HardwareKeyboardSettings"  
                         Description="Use to configure the settings for the hardware keyboard character repeats hold time and delay"  
                         Owner=""  
                         OwnerType="OEM"> 
      <Static>  
        <Settings Path="TextInput/HardwareKeyboard">  
          <Setting Name="AutoRepeatInitialDelay" Value="" />
          <Setting Name="KeyRepeatRate" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To specify the amount of time that the user must hold down a key before the keyboard character repeats, set the value for the `AutoRepeatInitialDelay` setting. The value is in milliseconds.

4.  To specify the amount of time to use as the delay between each keyboard character repeats, set the value for the `KeyRepeatRate` setting. The value is in milliseconds.

<a href="" id="testing-steps-"></a>**Testing Steps:**  
1.  Flash the build containing this customization to a phone with a hardware keyboard.

2.  Set up the phone. Press and hold down the same keyboard key. Verify that the amount of time needed to hold down a key before the keyboard character repeats corresponds to the value that you set. Also verify that the delay between each character repeat is equivalent to the value that you set.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
