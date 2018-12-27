---
title: Remove the trailing MSISDN digits on a SIM card
description: OEMs can remove the trailing MSISDN digits from the service provider name (SPN) in the device UI.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 43ee4fac-8a4c-4cd0-8395-5091aba3a1d8


ms.date: 05/02/2017
ms.topic: article


---

# Remove the trailing MSISDN digits on a SIM card


OEMs can remove the trailing MSISDN digits from the service provider name (SPN) in the device UI.

By default, the OS appends the trailing MSISDN digits to the service provider name (SPN) in the device UI, including on the device and messaging apps. If required by mobile operators, OEMs can use the `SimNameWithoutMSISDNEnabled` setting to remove the trailing MSISDN digits. However, you must use this setting together with `MultivariantProvisionedSPN` to suppress the MSISDN digits. For more information about how to use `MultivariantProvisionedSPN`, see [Change the default SIM name to match the SPN or operator name](change-the-default-sim-name-to-match-the-spn-or-operator-name.md).

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SimNameWithoutMSISDNEnabled"  
                         Description="Use to suppress the trailing MSISDN digits that are appended to the SPN in the device UI."  
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
          <Setting Name="SimNameWithoutMSISDNEnabled" Value="" />    
       </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `MultivariantProvisionedSPN` value to the name of the SPN or mobile operator. For more information, see [Change the default SIM name to match the SPN or operator name](change-the-default-sim-name-to-match-the-spn-or-operator-name.md).

4.  Set `SimNameWithoutMSISDNEnabled` to one of the following values:

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
    <td><p>Keeps the trailing MSISDN digits.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Removes the trailing MSISDN digits.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device that supports either a single or dual SIM.

2.  Boot the device and verify the following:

    -   The displayed friendly name for the SIM matches the SPN name or the value set for `MultivariantProvisionedSPN`. If there are two SIMs, verify that the displayed friendly names appear as expected for that SIM.

    -   If you set `SimNameWithoutMSISDNEnabled`=1, the trailing MSISDN digits should not appear. If there are two SIMs and both have `SimNameWithoutMSISDNEnabled`=1, both SIMs should not show the MSISDN digits in the UI.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
