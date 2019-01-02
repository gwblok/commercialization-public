---
title: Wi-Fi calling errors
description: OEMs can customize the mobile device to configure settings related to Wi-Fi calling errors.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: E3BF5E3A-755B-4B8F-B528-A89A30034B7F


ms.date: 05/02/2017
ms.topic: article


---

# Wi-Fi calling errors


OEMs can customize the mobile device to configure settings related to Wi-Fi calling errors, including:

-   Show an error message when a Wi-Fi calling error is reported by the modem.
-   Show a specific error message based on operator requirements.
-   Customize the generic error string when a Wi-Fi calling error happens.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WiFiCallingErrors"  
                         Description="Use to customize the Wi-Fi calling error settings."  
                         Owner=""  
                         OwnerType="OEM"> 

    <!-- Use for the per-IMSI case 

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

        <Settings Path="CellCore/PerIMSI/$(__IMSI)/CellUX">   
          <Setting Name="ShowWifiCallingError" Value="" />  
          <Setting Name="ShowSpecificWifiCallingError" Value="" />  
          <Setting Name="GenericWifiCallingErrorMessage" Value="" />  
        </Settings>  
      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
         <Settings Path="CellCore/PerDevice/CellUX">  
          <Setting Name="ShowWifiCallingError" Value="" />  
          <Setting Name="ShowSpecificWifiCallingError" Value="" />  
          <Setting Name="GenericWifiCallingErrorMessage" Value="" />   
        </Settings>  
      </Static>

    -->

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  To show the Wi-Fi calling error message in the mobile device UI, set `ShowWifiCallingError` to one of the following values:

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
    <td><p>0 or 'No'</p></td>
    <td><p>Shows the Wi-Fi calling error message.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the Wi-Fi calling error message.</p></td>
    </tr>
    </tbody>
    </table>



5.  To show the T-Mobile specific error message in the mobile device UI, set `ShowSpecificWifiCallingError` to one of the following values:

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
    <td><p>0 or 'No'</p></td>
    <td><p>Shows the Wi-Fi calling error message.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the Wi-Fi calling error message.</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  If the mobile device is not specific to T-Mobile, OEMs should use the `GenericWifiCallingErrorMessage` setting instead.
~~~



6.  To specify a custom generic Wi-Fi calling error string in the mobile device UI, set `GenericWifiCallingErrorMessage` to a string that corresponds to the error message you want to show. The string must not be longer than 127 characters.

<a href="" id="testing-"></a>**Testing:**  
Work with your mobile operator partner to understand the Wi-Fi calling error message requirements for the operator and to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
