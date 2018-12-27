---
title: View Internet APN
description: For mobile operators that require it, OEMs can show the View Internet APN button in the Cellular SIM settings page for users that have a data plan.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f938feac-d198-4b4d-8a8f-7e2f803e47d5


ms.date: 05/02/2017
ms.topic: article


---

# View Internet APN


For mobile operators that require it, OEMs can show the **View Internet APN** button in the **Cellular & SIM** settings page for users that have a data plan. When data is off, the button is disabled. By default, the button is hidden.

For dual SIM devices, the button is visible depending on the multivariant SIM settings. For example, if the data plan is on SIM1 and the setting is configured to hide the button, the **View Internet APN** button will be hidden. If the user switches to SIM2 and the setting is configured to show the button, the user will see the **View Internet APN** button.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ViewInternetAPN"  
                         Description="Use to show the 'View Internet APN' button in the cellular+SIM settings screen."  
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
          <!-- Use to show the 'View Internet APN' button in the cellular+SIM settings screen. 
               Set to 0 or 'No' (to hide, default) or set to 1 or 'Yes' (to show). -->
          <Setting Name="ShowViewAPN" Value="" />  
        </Settings>  
      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
         <Settings Path="CellCore/PerDevice/CellUX">  
          <!-- Use to show the 'View Internet APN' button in the cellular+SIM settings screen. Set to 0 or 'No' (to hide, default) or set to 1 or 'Yes' (to show). -->
          <Setting Name="ShowViewAPN" Value="" />         
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

4.  Set the value for `ShowViewAPN` to one of the following:

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
    <td><p>Hides the <strong>View Internet APN</strong> button in the <strong>Cellular + SIM</strong> settings screen.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Shows the <strong>View Internet APN</strong> button in the <strong>Cellular + SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a SIM.

2.  Go to the **Cellular & SIM** screen in **Settings**.

3.  Verify that the **View Internet APN** button is either hidden or visible depending on the value you set for `ShowViewAPN`.

    On a dual SIM device, verify if the **View Internet APN** button is hidden or visible depending on the `ShowViewAPN` setting value for each SIM.

4.  If there is no data plan associated with the SIM or data is turned off, verify that the button is disabled.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
