---
title: Use UTF-8 for MMS messages with unspecified character encoding
description: Some incoming MMS messages may not specify a character encoding. To properly decode MMS messages that do not specify a character encoding, OEMs can set UTF-8 to decode the message.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9710894f-83d2-49e1-9bb4-c3aebdf05139


ms.date: 05/02/2017
ms.topic: article


---

# Use UTF-8 for MMS messages with unspecified character encoding


Some incoming MMS messages may not specify a character encoding. To properly decode MMS messages that do not specify a character encoding, OEMs can set UTF-8 to decode the message.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="UseUTF8ForUnspecifiedCharset"  
                         Description="Use to set UTF-8 character encoding to decode incoming MMS messages that do not have a specified 
                                      character encoding."  
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
          <Setting Name="UseUTF8ForUnspecifiedCharset" Value="" />        
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the value of `UseUTF8ForUnspecifiedCharset` to one of the following:

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
    <td><p>Disables using UTF-8 for MMS messages with unspecified character encoding. This is the default behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Enables using UTF-8 for MMS messages with unspecified character encoding.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator to properly test this customization on their network.

To verify the customization:

1.  Use a device to send an MMS message without a character encoding specified to your Windows 10 Mobile device.

2.  Verify that the MMS was received correctly on your Windows 10 Mobile device. The message should not contain any unrecognized characters.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
