---
title: Audio volume limitation
description: OEMs can configure a setting to display a visual warning when the volume level of the phone exceeds a certain permitted threshold.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 94b0a786-2613-41d8-9faf-c5b688b2dce0


ms.date: 05/02/2017
ms.topic: article


---

# Audio volume limitation


OEMs can configure a setting to display a visual warning when the volume level of the phone exceeds a certain permitted threshold.

Some regions and markets have a volume limitation requirement, which limits the audio volume levels for portable devices like phones and MP3 players. To comply with this requirement, OEMs can configure a setting to display a visual warning when the volume level of the phone exceeds a certain permitted threshold (for example, 85 dB according to European Audio Standards) when audio is playing through the user’s headphones or device speakers. User acknowledgment is required before the volume limit is exceeded.

In addition, the phone will keep track of the amount of time that music and video is played at the permitted threshold and display the warning again if and when the user has been listening above the permitted threshold for at least 20 cumulative hours.

To reset the audio volume limit and show the volume level warning every time the volume level exceeds a certain permitted threshold, see [Reset the audio volume limitation and warning](reset-the-audio-volume-limitation-and-warning.md).

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="VolumeLimit"  
                         Description="Use to display a visual warning when the volume level exceeds a certain permitted threshold."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

       <Settings Path="VolumeLimit">  
          <Setting Name="EnableVolumeLimit" Value="" />  
          <Setting Name="VolumeLimit" Value="" />  
       </Settings> 

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `EnableVolumeLimit` to one of the following values:

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
    <td><p>Disables volume limits.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>Enables volume limits and displays a warning when the specified value for <code>VolumeLimit</code> is reached.</p></td>
    </tr>
    </tbody>
    </table>

     

4.  Set `VolumeLimit` to a value from 10 to 29 (inclusive). For devices sold in the EU, this value should map to 85 dB volume level. This value is also used as the maximum allowed volume in Kid's Corner for media volume.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  Steadily increase the volume and verify that a warning appears when the volume level has reached the limit that you have set.

3.  After accepting the warning, go to the music hub and select a song to play. After 20 hours of cumulative listening above the permitted volume threshold, verify that the warning is displayed again.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
