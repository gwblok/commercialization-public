---
title: Configuring boot battery charging behavior
description: The boot (UEFI) environment contains a battery charging application (owned by Microsoft) that is responsible for charging the battery in pre-boot and low power states.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2921db35-ce81-47cd-b28a-132379549980


ms.date: 05/02/2017
ms.topic: article


---

# Configuring boot battery charging behavior


The boot (UEFI) environment contains a battery charging application (owned by Microsoft) that is responsible for charging the battery in pre-boot and low power states. OEMs can configure some of the behavior of this application by using the registry values described in this topic.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
**Charging boot threshold**

OEMs can specify the threshold at which the device boots from UEFI-based charging to the Main OS. It is necessary to hold the device in the UEFI charging phase to charge the battery when it is too low to boot into the Main OS.

1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ChargeSettings"  
                         Description="Use to specify the threshold at which the device boots from UEFI-based charging to the main OS and to enable power-off charging mode."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="ChargeSettings">  
          <Setting Name="ChargingBootThreshold" Value="" />  
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value` to a threshold value between 1 and 10. Microsoft recommends that OEMs calibrate this value so that the device spends a minimal amount of time in the threshold charging mode.

    **Note**  
    In Windows 10 Mobile, the UEFI charging app included in the OS is being deprecated. Microsoft recommends that OEMs use the app published by the SoC vendor. If you use the SoC vendor’s app, make sure that you disable the Windows 10 app by updating ChargingBootThreshold to 255 (hex 0xFF).

     

**Power-off charging**

This setting enables *power-off charging*. Power-off charging allows the device to charge while it appears off to the user. In power-off charging mode, the device does not boot to the OS when plugged in. Instead, the device waits for the user to press and hold the power button before booting to the OS.

**Important**  
Power-off charging can only be configured when the device image is generated. Windows 10 Mobile does not provide a way for users to enable or disable power-off charging.

 

1.  Create a customization answer file using the contents shown in the following code sample or use the sample ChargeSettings.xml file.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ChargeSettings"  
                         Description="Use to specify the threshold at which the device boots from UEFI-based charging to the main OS and to enable power-off charging mode."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="ChargeSettings">  
          <Setting Name="PowerOffChargingEnabled" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value` to 1 to enable power-off charging or to 0 to disable power-off charging.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
