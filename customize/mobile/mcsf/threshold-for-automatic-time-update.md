---
title: Threshold for automatic time update
description: For mobile networks that support Network Identity and Time Zone (NITZ), OEMs can specify the difference (in number of seconds) between the NITZ information and the current device time before a device time update is triggered.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d5793eda-9b34-4c14-b225-3db9c38a95db


ms.date: 05/02/2017
ms.topic: article


---

# Threshold for automatic time update


For mobile networks that support Network Identity and Time Zone (NITZ), OEMs can specify the difference (in number of seconds) between the NITZ information and the current device time before a device time update is triggered. When set, the OS updates the device time if the time difference is larger than the value specified by the OEM.

The threshold must be a value between 1 and 59 seconds, inclusive.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="NetworkTimeUpdateThreshold"  
                         Description="Use to specify the difference (in seconds) between the NITZ information and the current 
                                      device time before a device time update is triggered."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  
        <Settings Path="AutomaticTime">  
          <Setting Name="NetworkTimeUpdateThreshold" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value for `NetworkTimeUpdateThreshold` between 1 and 59 seconds (inclusive). This is equivalent to 0x1 and 0x3B (inclusive) in hexadecimal.

<a href="" id="testing-"></a>**Testing:**  
Flash the build containing this customization to a phone connected to a network that supports NITZ.

**Note**  
OEMs may need to configure the value a few times to determine the best threshold value.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
