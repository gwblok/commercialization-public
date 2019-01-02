---
title: Change the default SIM name to match the SPN or operator name
description: By default, the OS displays SIM 1 or SIM 2 as the default friendly name for the SIM in slot 1 or slot 2 if the service provider name (SPN) or mobile operator name has not been set.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d40bb857-5496-459d-bcc7-38833a2db4c2


ms.date: 05/02/2017
ms.topic: article


---

# Change the default SIM name to match the SPN or operator name


By default, the OS displays **SIM 1** or **SIM 2** as the default friendly name for the SIM in slot 1 or slot 2 if the service provider name (SPN) or mobile operator name has not been set. Partners can use this customization to change the default name read from the SIM to define the SPN for SIM cards that do not contain this information or to generate the default friendly name for the SIM.

The OS uses the default value as the display name for the SIM or SPN in the Start screen and other parts of the UI including the SIM settings screen. For dual SIM phones that contain SIMs from the same mobile operator, the names that appear in the UI may be similar.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MultivariantProvisionedSPN"  
                         Description="Use to define the SPN for SIM cards that don't contain this information or use to
                                      generate the default friendly name for the SIM."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <!-- Define the Targets --> 
      <Targets>
         <Target Id="">
            <TargetState>
               <Condition Name="" Value="" />
               <Condition Name="" Value="" />
            </TargetState>
         </Target>
      </Targets>
      
      <Static>
        <Settings Path="Multivariant">
          <Setting Name="Enable" Value="1" />
        </Settings>
        <Settings Path="AutoDataConfig">
          <Setting Name="Enable" Value="0" />
        </Settings>
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>

        <Settings Path="CellCore/PerIMSI/$(__IMSI)/General/Critical">  
          <Setting Name="MultivariantProvisionedSPN" Value="" />    
       </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `MultivariantProvisionedSPN` value to the name of the SPN or mobile operator.

    The following table shows the scenarios supported by this customization:

    > [!NOTE]
    > In the **Default SIM name** column:
    > -   The **" "** in *MultivariantProvisionedSPN*" "1234 means that there is a space between the mobile operator name or SPN and the last 4 digits of the MSISDN.
    > -   *MultivariantProvisionedSPN* means the value that you set for the `MultivariantProvisionedSPN` setting.
    > -   *SIM 1* or *SIM 2* is the default friendly name for the SIM in slot 1 or slot 2.

    | Multivariant setting set? | SPN provisioned? | MSISDN (last 4 digitis: 1234, for example) provisioned? | Default SIM name                                                        |
    |---------------------------|------------------|---------------------------------------------------------|-------------------------------------------------------------------------|
    | Yes                       | Yes              | Yes                                                     | *MultivariantProvisionedSPN*1234 or *MultivariantProvisionedSPN*" "1234 |
    | Yes                       | No               | No                                                      | *MultivariantProvisionedSPN* (up to 16 characters)                      |
    | Yes                       | Yes              | No                                                      | *MultivariantProvisionedSPN* (up to 16 characters)                      |
    | Yes                       | No               | Yes                                                     | *MultivariantProvisionedSPN*1234 or *MultivariantProvisionedSPN*" "1234 |
    | No                        | Yes              | Yes                                                     | If SPN string >= 12: *SPN*1234<br/>If SPN string < 12: *SPN*" "1234     |
    | No                        | No               | No                                                      | *SIM 1* or *SIM 2*                                                      |
    | No                        | Yes              | No                                                      | SPN (up to 16 characters)                                               |
    | No                        | No               | Yes                                                     | *SIM 1* or *SIM 2*                                                      |

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone that supports either a single or dual SIM.

2.  Boot the phone and verify that the displayed friendly name for the SIM matches the SPN name or the value set for `MultivariantProvisionedSPN`.

    If there are two SIMs, verify that the displayed friendly names appear as expected.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
