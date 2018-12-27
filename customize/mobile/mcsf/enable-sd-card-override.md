---
title: Enable SD card override
description: By default, using the SD card for device updates is disabled. OEMs who want to use the SD card for device updates must set EnableSDCardOverride to opt-in and re-enable updates using the SD card.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7f2f619b-7353-4221-a06b-179562d6d41e


ms.date: 05/02/2017
ms.topic: article


---

# Enable SD card override


By default, using the SD card for device updates is disabled. OEMs who want to use the SD card for device updates must set **EnableSDCardOverride** to opt-in and re-enable updates using the SD card. However, if OEMs set **BlockUsingSDCard** in [Block using SD card for updates](block-using-sd-card-for-updates.md), the value set for **BlockUsingSDCard** takes precedence.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableSDCardOverride"  
                         Description="Use to configure whether the SD card can be used for updates on the device."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="DeviceUpdate">  
          <!-- Set the value to 0 or 'No' (do not use the SD card for updates), or set to 1 or 'Yes' (use the SD card for updates). -->
          <Setting Name="EnableSDCardOverride" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `EnableSDCardOverride` to one of the following:

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
    <td><p>Block the use of the SD card for phone updates.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Enable use of the SD card for phone updates.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  Fill the Data partition and leave only 11 to 100 MB of available space.

3.  To verify if the SD card is used for updates, look for the following message in the Installation ARD:

    **WARNING: Do not remove your SD card while the update installs.**

4.  If you set `EnableSDCardOverride` to allow the use of the SD card for updates and your phone supports an SD card, and `BlockUsingSDCard` is not enabled, verify that you're able to use the SD card for device updates.

5.  If you set `EnableSDCardOverride` to allow the use of the SD card for updates and your phone supports an SD card, but `BlockUsingSDCard` is enabled, verify that you're not able to use the SD card for device updates.

To verify the update scenario, try adding a new keyboard in the **Settings** &gt; **Keyboard** &gt; **add keyboards** screen and then select a new keyboard to add. This scenario uses the same path as device updates but is faster and does not require uploading builds to the update preview server.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
