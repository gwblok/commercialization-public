---
title: Block using SD card for updates
description: For devices that support an SD card, OEMs can either allow or block the use of the SD card for device updates.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4a215003-8b89-4756-8797-c7b73607049e


ms.date: 05/02/2017
ms.topic: article


---

# Block using SD card for updates


For devices that support an SD card, OEMs can either allow or block the use of the SD card for device updates.

By default, this customization is not set and the OS can use the SD card for updates. If there is enough space on the *e*MMC to download an update, the OS will use the *e*MMC instead of the SD card.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>  
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                        Name="BlockUsingSDCard"  
                        Description="Use to determine whether to block the use of the SD card for device updates."  
                        Owner=""  
                        OwnerType="OEM"> 

     <Static>  

       <Settings Path="DeviceUpdate">  
         <Setting Name="BlockUsingSDCard" Value="" />    
      </Settings>  

     </Static>

   </ImageCustomizations>
   ```

2. Specify an `Owner`.

3. Set the value of `BlockUsingSDCard` to one of the following:

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
   <td><p>0 or &#39;No&#39;</p></td>
   <td><p>Do not block the use of the SD card for device updates.</p>
   <div class="alert">
   <strong>Note</strong><br/><p>Make sure that your UEFI supports powering up the SD card on the UpdateOS.</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td><p>1 or &#39;Yes&#39;</p></td>
   <td><p>Block the use of the SD card for device updates.</p></td>
   </tr>
   </tbody>
   </table>



<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  If you set `BlockUsingSDCard` to allow the use of the SD card for updates and your device supports an SD card, if space on the *e*MMC is not enough for the update, the OS will choose the SD card to use for the update.

    When there is an update available and you have synced and downloaded the update, verify whether the update was installed from the SD card.

3.  When the update has been successfully installed, use GetDULogs.exe to check if the update was done through the SD card.

    Make sure that your UEFI supports the powering up of the SD card on the UpdateOS.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
