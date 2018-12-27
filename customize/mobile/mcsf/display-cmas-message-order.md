---
title: Display CMAS message order
description: Partners can configure the order in which newly received CMAS alert messages are displayed on the device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4c6fb6f9-7b8e-499f-828d-08c80389d417


ms.date: 05/02/2017
ms.topic: article


---

# Display CMAS message order


Partners can configure the order in which newly received CMAS alert messages are displayed on the device.

If the device receives at least one CMAS alert message which has not been acknowledged by the user, and another CMAS alert message arrives on the device, partners can configure the order in which the newly received alert messages are displayed on the device regardless of the service category of the alert. Users will not be able to change the display order once it has been set.

If partners do not specify a value for this customization, the default first in/first out (FIFO) display order is used.

Users will be able to acknowledge the messages in the reverse order they were received.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisplayCmasLifo"  
                         Description="Use to configure the order for displaying new CMAS alert messages."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Messaging/GlobalSettings">  
          <Setting Name="DisplayCmasLifo" Value="" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value` to one of the following:

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
    <td><p>Sets a First in/first out (FIFO) message order. Users will not be able to see newer alert messages until they have dismissed the previous alert message(s).</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Sets a Last in/first out (LIFO) message order. Newer alert messages will immediately appear on top of older alert messages.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing Steps:**  
Work with your mobile operator partner to fully test this customization on their network.

Verify that the order in which CMAS alert messages are displayed on the device that contains the customization matches the setting (FIFO or LIFO) that you have specified.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
