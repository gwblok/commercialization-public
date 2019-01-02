---
title: Additional Internet APN settings
description: OEMs can hide both the add internet apn button and the IP type listbox in the internet APN settings screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 688c9a86-91dc-40c3-8d88-dd07202b4270


ms.date: 05/02/2017
ms.topic: article


---

# Additional Internet APN settings


OEMs can hide both the **add internet apn** button and the **IP type** listbox in the **internet APN** settings screen.

If it is required by the mobile operator OEMs can hide the **add internet apn** button, which enables the user to manually add and configure a data connection for a network. OEMs can also hide the **IP type** listbox in the **internet APN** settings screen.

**Limitations and restrictions**:

-   Partners must not provide an alternate user interface for adding or editing APN values.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="InternetAPNSettings"  
                         Description="Use to hide or show the 'add internet apn' button in the SIM settings screen,
                                      and hide or show the 'IP type' setting in the internet APN settings screen."  
                         Owner=""  
                         OwnerType="OEM"> 


~~~
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
      <Setting Name="HideAPN" Value="" />  
      <Setting Name="HideAPNIPType" Value="" />      
      <Setting Name="APNIPTypeIfHidden" Value="" />      
    </Settings>  
  </Variant>

-->

<!-- Use for the per-device case

  <Static>  
     <Settings Path="CellCore/PerDevice/CellUX">  
      <Setting Name="HideAPN" Value="" />  
      <Setting Name="HideAPNIPType" Value="" />      
      <Setting Name="APNIPTypeIfHidden" Value="" />      
    </Settings>  
  </Static>

-->

</ImageCustomizations>
```
~~~

2.  Specify an `Owner`.

3.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  Set the value for `HideAPN` to one of the following:

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
    <td><p>Shows the <strong>add internet APN</strong> button in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>add internet APN</strong> button in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>



5.  Set the value for `HideAPNIPType` to one of the following:

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
    <td><p>Shows the <strong>IP type</strong> listbox in the <strong>internet APN</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>IP type</strong> listbox in the <strong>internet APN</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>



6.  To change the default IP type shown in the **IP type** listbox: Set the value for `APNIPTypeIfHidden` to one of the following:

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
    <td><p>2 or 'IPV4V6'</p></td>
    <td><p>Sets the default IP type to IPv4v6.</p></td>
    </tr>
    <tr class="even">
    <td><p>3 or 'IPV4V6XLAT'</p></td>
    <td><p>Sets the default IP type to IPv4v6 XLAT.</p></td>
    </tr>
    </tbody>
    </table>



<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Go to the **cellular & SIM** screen in **Settings**.

3.  Verify that the **add internet apn** button is no longer visible if configured to be hidden.

4.  Tap the **add internet apn** button. Depending on the setting, verify that:

    1.  The **IP type** setting either shows a dropdown listbox with **IPv4**, **IPv6**, **IPv4v6**, or **IPv4v6 464XLAT**. Or,

    2.  The **IP type** setting is hidden.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
