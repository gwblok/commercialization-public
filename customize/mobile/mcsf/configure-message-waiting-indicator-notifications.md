---
title: Configure message waiting indicator notifications
description: Depending on the scenario that partners want to support, partners can configure the voicemail system so the device either ignores or responds to message waiting indicator (MWI) notifications.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9aacfb22-1f75-459f-a4c7-4fde597e0f26


ms.date: 05/02/2017
ms.topic: article


---

# Configure message waiting indicator notifications


Depending on the scenario that partners want to support, partners can configure the voicemail system so the device either ignores or responds to message waiting indicator (MWI) notifications.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="IgnoreMWINotifications"  
                         Description="Use to configure the voicemail system so the phone either ignores or responds to message waiting indicator (MWI) notifications."  
                         Owner=""  
                         OwnerType="OEM"> 


~~~
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

    <Settings Path="Phone/PerSimSettings/$(__IMSI)"> 
      <Setting Name="IgnoreMWINotifications" Value="" />      
    </Settings>  

  </Variant>

</ImageCustomizations>
```
~~~

2.  Specify an `Owner`.

3.  For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  Set `IgnoreMWINotifications` to one of the following values:

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
    <td><p>MWI functions normally and the user is notified that voicemails are available.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>MWI notifications are ignored by the device.</p></td>
    </tr>
    </tbody>
    </table>



~~~
If `IgnoreMWINotifications` is not present, MWI functions normally and the user is notified when voicemails are available.
~~~

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device that has a UICC.

2.  On another phone, call the number for the device that contains the customization. Leave a voicemail message.

3.  If visual voicemail has not been set up on the device, you can verify that the customization worked by checking if the device tile shows a voicemail notification.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
