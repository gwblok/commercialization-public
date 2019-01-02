---
title: Hide call forwarding
description: Partners can hid the user option for call forwarding.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: aa253358-9422-439f-8202-afb5957279e0


ms.date: 05/02/2017
ms.topic: article


---
# Hide call forwarding

Partners can hide the user option for call forwarding.

By default, users can decide whether to turn on call forwarding. Partners can hide this user option so that call forwarding is permanently disabled.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HideCallForwarding"  
                         Description="Use to hide user option for call forwarding to users."  
                         Owner=""  
                         OwnerType="OEM"> 
    <Static>
        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="HideCallForwarding" Value="" />      
        </Settings>  
    </Static>
    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `HideCallForwarding` to one of the following values:

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
    <td><p>0 or False</p></td>
    <td><p>Shows the user option to make it possible for users to forward calls.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or True</p></td>
    <td><p>Hides the user option</p></td>
    </tr>
    </tbody>
    </table>



~~~
By default, the hide call forwarding UI is set to 0 or always shown.
~~~

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
