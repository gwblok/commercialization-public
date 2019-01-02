---
title: International assisted dialing for SMS
description: If partners have turned off Assistance for dialing international phone numbers, partners may still override the MCC and MNC used for plus code replacement when sending SMS.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a634fb89-bb8d-44bd-b5c7-4064828515ec


ms.date: 05/02/2017
ms.topic: article


---

# International assisted dialing for SMS


If partners have turned off [Assistance for dialing international phone numbers](assistance-for-dialing-international-phone-numbers.md), partners may still override the MCC and MNC used for plus code replacement when sending SMS. These values are used to generate the correct IDD. This change applies regardless of roaming status. By setting `AssistedDialingMcc` and `AssistedDialingMnc`, international assisted dialing will be enabled for SMS if the user setting for international assisted dialing is enabled.

For devices that support IMS over SMS, partners can override support for the assisted dialing plus (**+**) code for SMS by setting `AssistedDialingPlusCodeSupportOverride`. If enabled, the OS will not convert the plus (**+**) code to the proper assisted number when the user turns on the dialing assist option.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SMSAssistedDialing"  
                         Description="Use to override the MCC and MNC used for sending SMS messages."  
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

        <Settings Path="Messaging/PerSimSettings/$(__ICCID)">  
          <Setting Name="AssistedDialingMcc" Value="" />
          <Setting Name="AssistedDialingMnc" Value="" />     

         <!-- For an IMS over SMS supported device, partners can override the assisted dialing plus code support for SMS.
          <Setting Name="AssistedDialingPlusCodeSupportOverride" Value="" />
          -->
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the values for the following settings to enable international assistance dialing for SMS:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Setting</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><code>AssistedDialingMcc</code> : REG_SZ</p></td>
    <td><p>The Mobile Country Code (MCC) to use for sending SMS.</p></td>
    </tr>
    <tr class="even">
    <td><p><code>AssistedDialingMnc</code> : REG_SZ</p></td>
    <td><p>The Mobile Network Code (MNC) to use for sending SMS.</p></td>
    </tr>
    </tbody>
    </table>

     

6.  For a device that supports IMS over SMS, you can override the support for the assisted dialing plus (**+**) code for SMS. To do this, set `AssistedDialingPlusCodeSupportOverride` to one of the following values:

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
    <td><p>0 or 'False'</p></td>
    <td><p>Don't override the assisted dialing plus code support.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Override the assisted dialing plus code support. The OS will not convert the plus (<strong>+</strong>) code to the proper assisted number when the user turns on the dialing assist option.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
