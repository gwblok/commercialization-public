---
title: Conditional call forwarding
description: Partners can now show the call forwarding icon for conditional call forwarding as well as unconditional call forwarding.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e4e48842-bcf1-40ec-8012-bf34cb92f121


ms.date: 05/02/2017
ms.topic: article


---

# Conditional call forwarding


Partners can now show the call forwarding icon for conditional call forwarding as well as unconditional call forwarding.

Partners should not enable this feature for networks that support voicemail, which is implemented on the network as conditional call forwarding so the call forwarding icon would also be on.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ConditionalCallForwardingIcon"  
                         Description="Use to show the call forwarding icon for conditional call forwarding as well as unconditional call forwarding."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Shell/SystemTray/ConditionalCallForwarding">  
          <!-- Set the value to 0 or 'Disabled' (shows the icon for unconditional call forwarding only), or
               set to 1 or 'Enabled' (shows the icon for both conditional and unconditional call forwarding) -->
          <Setting Name="ConditionalCallForwardingIcon" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `ConditionalCallForwardingIcon` to one of the following values:

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
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Only unconditional forwarding will indicate call forwarding. This is the default.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>Both conditional and unconditional forwarding will indicate call forwarding.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a UICC.

2.  Set conditional call forwarding using the following USDD codes as specified in the topic [Supplementary services exclusions](supplementary-services-exclusions.md):

    -   61 (FWDNOREPLY)

    -   62 (FWDNOTREACHABLE)

    -   67 (FWDBUSY)

3.  Depending on the market, verify that the call forwarding icon appears based on the `IndicateConditionalCallForwarding` registry setting.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
