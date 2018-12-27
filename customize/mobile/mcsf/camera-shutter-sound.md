---
title: Camera shutter sound
description: The camera shutter sound that occurs when the user takes a picture or starts filming a video can be turned off by removing the Camera shutter option from the Sounds settings screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d146404c-f5b6-436f-9701-91d282e3c942


ms.date: 05/02/2017
ms.topic: article


---

# Camera shutter sound


The camera shutter sound that occurs when the user takes a picture or starts filming a video can be turned off by removing the **Camera shutter** option from the **Sounds** settings screen.

This customization affects all camera apps on the mobile device. If camera sounds are not enforced, camera sounds will respond to the ringer and notification volume and sounds will not play through the combo device.

**Limitations and restrictions**:

-   OEMs can remove this user setting only for markets in which the camera shutter sound is a legally required component due to privacy laws.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CameraShutterSound"  
                         Description="Use to turn off the camera shutter sound by removing the Camera shutter toggle 
                                      from the Settings CPL."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Camera">  
          <Setting Name="ShutterSoundUI" Value="0" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `ShutterSoundUI``Value` to one of the following:

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
    <td><p>0 or 'Hide'</p></td>
    <td><p>Hides the <strong>Camera shutter</strong> option from the <strong>Sounds</strong> settings screen.</p>
    <p>When set to this value, the enforced shutter sound is on. This value enforces playback of camera sounds and sound will play through the combo device when the wired headset is plugged in.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Show'</p></td>
    <td><p>Shows the <strong>Camera shutter</strong> option from the <strong>Sounds</strong> settings screen. This is the default.</p>
    <p>When set to this value, the enforced shutter sound is off.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image containing this customization to a phone.

2.  Go to the **Sounds** settings screen.

3.  Scroll down and verify that the **Camera shutter** setting is no longer visible.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
