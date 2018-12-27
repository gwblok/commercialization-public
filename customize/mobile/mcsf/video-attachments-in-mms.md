---
title: Video attachments in MMS
description: Partners can specify the transcoding to use for video files sent as attachments in MMS messages.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 78ef9c04-2eaf-4c52-80c0-f595c4e8759a


ms.date: 05/02/2017
ms.topic: article


---

# Video attachments in MMS


Partners can specify the transcoding to use for video files sent as attachments in MMS messages.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="TargetVideoFormat"  
                         Description="Use to specify the transcoding to use for video files sent as attachments in MMS messages."  
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
          <Setting Name="TargetVideoFormat" Value="" />             
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set `TargetVideoFormat` to one of the following values to configure the default transcoding for video files sent as attachments in MMS messages:

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
    <td><p>0 or 0x0</p></td>
    <td><p>Sets the transcoding to H.264 + AAC + MP4. This is the default set by the OS.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 0x1</p></td>
    <td><p>Sets the transcoding to H.264 + AAC + 3GP.</p></td>
    </tr>
    <tr class="odd">
    <td><p>2 or 0x2</p></td>
    <td><p>Sets the transcoding to H.263 + AMR.NB + 3GP.</p></td>
    </tr>
    <tr class="even">
    <td><p>3 or 0x3</p></td>
    <td><p>Sets the transcoding to MPEG4 + AMR.NB + 3GP.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Attempt to send a message with an attachment that requires the new transcoding. Verify that the message sends and that the file can be opened after it is received.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
