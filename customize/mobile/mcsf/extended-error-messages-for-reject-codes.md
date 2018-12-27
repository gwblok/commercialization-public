---
title: Extended error messages for reject codes
description: When a reject code is sent by the network, partners can specify that extended error messages should be displayed instead of the standard simple error messages.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9adeea76-3242-457e-9717-32cee3f6672a


ms.date: 05/02/2017
ms.topic: article


---

# Extended error messages for reject codes


When a reject code is sent by the network, partners can specify that extended error messages should be displayed instead of the standard simple error messages. This customization is intended for use only when required by the mobile operator’s network.

The short versions of the extended reject message are shown in the following screens:

-   **Phone** tile in **Start**

-   **Call History** screen

-   Dialer

-   **Call Progress** screen

-   **Incoming Call** screen

-   As the status string under **Settings** &gt; **Cellular & SIM**

The long version of the extended reject message is shown in the following screen:

-   Under the **Active Network** label in **Settings** &gt; **Cellular & SIM**

The OS handles three extended reject codes:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Reject code</th>
<th>Long version</th>
<th>Short version</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 (The SIM card hasn’t been activated or has been deactivated)</p></td>
<td><p>SIM not set up MM#2</p></td>
<td><p>Invalid SIM</p></td>
</tr>
<tr class="even">
<td><p>3 (The SIM card fails authentication or one of the identity check procedures. This can also happen due to a duplication of the TMSI across different MSCs)</p></td>
<td><p>Can’t verify SIM MM#3</p></td>
<td><p>Invalid SIM</p></td>
</tr>
<tr class="odd">
<td><p>6 (The device has been put on a block list, such as when the device has been stolen or the IMEI is restricted)</p></td>
<td><p>Phone not allowed MM#6</p></td>
<td><p>No Service</p></td>
</tr>
</tbody>
</table>



<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ExtendedRejectCodes"  
                         Description="Use to specify that extended error messages should be displayed instead of standard simple messages."  
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
      <Setting Name="ShowExtendedRejectCodes" Value="" />    
    </Settings>  
  </Variant>

-->

<!-- Use for the per-device case

  <Static>  
     <Settings Path="CellCore/PerDevice/CellUX">  
      <Setting Name="ShowExtendedRejectCodes" Value="" />   
    </Settings>  
  </Static>

-->

</ImageCustomizations>
```
~~~

2.  Specify an `Owner`.

3.  Set the `Branding flags` setting in the [Branding for phone calls](branding-for-phone-calls.md) customization so that the ExtendedRejectCodes flag is enabled.

    **Note**  
    The ExtendedRejectCodes flag is not enabled by default so make sure that this is set. Both the `ShowExtendedRejectCodes` setting and ExtendedRejectCodes flag need to be set for the customization to be fully enabled.



4.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the value for `ShowExtendedRejectCodes` to one of the following:

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
    <td><p>Hides the extended error messages when devices receive LAU reject codes with cause number 2, 3, or 6.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Shows the extended error messages when devices receive LAU reject codes with cause number 2, 3, or 6.</p></td>
    </tr>
    </tbody>
    </table>



~~~
The default for this setting is to show the **CDMA** option in the **Mode** selection drop-down that appears in the **Cellular & SIM** settings screen.
~~~

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Verify that extended error messages shown on the device when a reject code is sent by the network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
