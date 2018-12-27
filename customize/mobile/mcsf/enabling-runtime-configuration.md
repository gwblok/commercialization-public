---
title: Enabling runtime configuration
description: Runtime configuration, or multivariant, provides a generic mechanism for creating a single image that can work for multiple markets and reduce the number of images that OEMs need to create, manage, and test.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9099d7c2-35fb-4b9a-be8e-aa598df0da7f


ms.date: 05/02/2017
ms.topic: article


---

# Enabling runtime configuration


Runtime configuration, or multivariant, provides a generic mechanism for creating a single image that can work for multiple markets and reduce the number of images that OEMs need to create, manage, and test. By default, runtime configuration is enabled and ADC is turned off. Only one or the other must be turned on. So, if an OEM wants to disable runtime configuration, they must enable ADC.

The OS will handle different scenarios depending on whether runtime configuration has been enabled so OEMs should take into consideration the scenarios they are trying to enable.

**Note**  
By enabling runtime configuration, SIM-based language detection will also be enabled.

 

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableRuntime configuration"  
                         Description="Use to enable runtime configuration."
                         Owner=""  
                         OwnerType="OEM"> 

       <Static>
          <!-- Turns on runtime configuration -->
          <Settings Path="Multivariant">  
             <Setting Name="Enable" Value="1" /> 
          </Settings>  
          <!-- Turns off ADC -->
          <Settings Path="AutoDataConfig">  
             <Setting Name="Enable" Value="0" /> 
          </Settings>  
       </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  The above code example shows the default setting. Only one can be turned on (or enabled), and the other must be turned off (or disabled). Depending on what you want to do, you can use one of the following values:

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
    <td><p>Disables the feature</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>Enables the feature</p></td>
    </tr>
    </tbody>
    </table>

     

The registry key for enabling or disabling runtime configuration is below. This registry key can have a value of 1 or 0 where 1 represents enabled and 0 represents disabled.

```
HKLM\software\microsoft\multivariant\enable
```

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
