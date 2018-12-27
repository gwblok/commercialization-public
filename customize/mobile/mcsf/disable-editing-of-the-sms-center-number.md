---
title: Disable editing of the SMS center number
description: To meet market or mobile operator requirements, OEMs can configure a setting to prevent users from editing the SMS center number in the messaging settings CPL.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5b32c687-18f3-4874-bdcd-98a504018358


ms.date: 05/02/2017
ms.topic: article


---

# Disable editing of the SMS center number


To meet market or mobile operator requirements, OEMs can configure a setting to prevent users from editing the **SMS center number** in the messaging settings CPL.

By default, the setting does not exist and users can edit the **SMS center number**. A warning statement related to the changing the SMS center number is also displayed below the SMS center number.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SmscPanelDisabled"  
                         Description="Use to prevent users from editing the 'SMS center number' in the messaging settings CPL."  
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
          <Setting Name="SmscPanelDisabled" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set `SmscPanelDisabled` to one of the following values:

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
    <td><p>1 or 'True'</p></td>
    <td><p>Disables editing of the <strong>SMS center number</strong> and hides the warning statement.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'False'</p></td>
    <td><p>Enables users to edit the <strong>SMS center number</strong>.</p>
    <p>This is the default behavior.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build that contains this customization to a device.

2.  Go to the **Messaging** settings screen.

3.  Verify that the correct settings option is enabled depending on the default value that you set.

    -   If `SmscPanelDisabled` is set to 1 or 'True', verify that the **SMS center number** cannot be edited.

    -   If `SmscPanelDisabled` is set to 0 or 'False', verify that the **SMS center number** can be edited and the warning text below this option is visible.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
