---
title: MMS APN settings
description: Partners can choose to display an add mms apn or edit mms apn button that enables the user to configure the APN used for MMS.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4e35af49-40a6-44dd-acda-10879cd7b03f


ms.date: 05/02/2017
ms.topic: article


---

# MMS APN settings


Partners can choose to display an **add mms apn** or **edit mms apn** button that enables the user to configure the APN used for MMS. APN values entered by the user are not verified and may not work. The user-entered APN is always used if available; it is not overridden by ADC or over the air updates.

**Limitations and restrictions**:

-   If partners have set a list of permitted push proxy gateways, any user-entered APN that does not match with a PPG value in the list will fail to work.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CellularSettings"  
                         Description="Use to display an 'add mms apn' or 'edit mms apn' button to enable users to configure the APN used for MMS."  
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
          <!-- Hides or shows the 'add mms apn' button in the SIM settings page.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="HideMMSAPN" Value="" />      

          <!-- Hides or shows the 'IP type' setting in the MMS APN settings screen.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="HideMMSAPNIPType" Value="" />  

          <!-- Changes the default IP type.Set to 0 or 'IPV4' (for IPv4), 1 or 'IPV6' (for IPv6), or 2 or 'IPV4V6' (for IPv4v6). -->
          <Setting Name="MMSAPNIPTypeIfHidden" Value="" />   
        </Settings>  
      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
         <Settings Path="CellCore/PerDevice/CellUX">  
          <!-- Hides or shows the 'add mms apn' button in the SIM settings page.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="HideMMSAPN" Value="" />   

          <!-- Hides or shows the 'IP type' setting in the MMS APN settings screen.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="HideMMSAPNIPType" Value="" />   

          <!-- Changes the default IP type.Set to 0 or 'IPV4' (for IPv4), 1 or 'IPV6' (for IPv6), or 2 or 'IPV4V6' (for IPv4v6). -->
          <Setting Name="MMSAPNIPTypeIfHidden" Value="" />     
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

4.  To hide or show the **add mms apn** button in the SIM settings screen: Set the value for `HideMMSAPN` to one of the following:

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
    <td><p>Shows the <strong>add mms apn</strong> button in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>add mms apn</strong> button in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>

     

5.  To hide or show the **IP type** setting in the MMS APN settings screen: Set the value for `HIdeMMSAPNIPType` to one of the following:

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
    <td><p>Shows the <strong>IP type</strong> setting in the MMS APN settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>IP type</strong> drop-down in the MMS APN settings screen.</p></td>
    </tr>
    </tbody>
    </table>

     

6.  To change the default IP type shown in the **IP type** settings drop-down: Set the value for `MMSAPNIPTypeIfHidden` to one of the following:

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
    <td><p>0 or 'IPV4'</p></td>
    <td><p>Sets the default IP type to IPv4.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'IPV6'</p></td>
    <td><p>Sets the default IP type to IPv6.</p></td>
    </tr>
    <tr class="odd">
    <td><p>1 or 'IPV4V6'</p></td>
    <td><p>Sets the default IP type to IPv4v6.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  If the **add mms apn** button is configured to be hidden:

    -   Go to the **Messaging** settings screen and verify that the **add mms apn** button is no longer visible.

    -   Go to the **Cellular & SIM** settings screen and verify that the **add mms apn** button is no longer visible.

3.  If the **add mms apn** button is not configured to be hidden, tap the button and verify that the **IP type** setting either shows the correct default value or is hidden.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
