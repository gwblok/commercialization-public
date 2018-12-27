---
title: SMS intercept ports
description: OEMs can configure ports on which a Wireless Application Protocol (WAP)-formatted message can be intercepted by the mobile operator app.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 910e490e-ddbf-4311-8957-0128ae226bb7


ms.date: 05/02/2017
ms.topic: article


---

# SMS intercept ports


OEMs can configure ports on which a Wireless Application Protocol (WAP)-formatted message can be intercepted by the mobile operator app.

Certain mobile operators require the ability to intercept SMS messages for processing by a mobile operator app rather than by the standard Microsoft messaging app. To meet these operator requirements, OEMs can specify string filters in a deny list to be matched against incoming SMS messages intended for operator partner apps that are not installed on the device. For more information on how to do this, see [SMS intercept deny list](sms-intercept-deny-list.md). In addition, operators can also require the ability to configure the port on which a Wireless Application Protocol (WAP)-formatted message can be intercepted by the mobile operator app. The incoming WAP message must have its destination port set to be one of the configured ports in order for the message to be accepted. To configure the correct port, OEMs can use the `SmsInterceptPorts` setting that's documented in this topic.


<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SMSInterceptPorts"  
                         Description="Use to specify one or more ports on which a WAP-formatted message can be intercepted by a mobile operator app."  
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
          <Setting Name="SmsInterceptPorts" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the `SmsInterceptPorts` value to one or more ports on which a WAP-formatted message can be intercepted by the custom MO app. For example, *4100;04102;04456* and so on.

    **Caution**  
    Any port number can be configured except for 2948, which is the standard port of a WAP push.

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator partner to correctly test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
