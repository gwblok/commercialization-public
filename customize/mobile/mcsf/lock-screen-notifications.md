---
title: Lock screen notifications
description: OEMs can preload apps that support lock screen notifications.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 09fe0edd-60cf-4bb1-a0d0-b0393574fa69


ms.date: 05/02/2017
ms.topic: article


---

# Lock screen notifications


OEMs can preload apps that support lock screen notifications. Notifications alert the user to new content or updates in that app. They can take the form of a number (to indicate the number of changes) or a text preview.

OEMs can also preset one notification in the fifth slot on the lock screen. This notification displays an icon for a single app plus the number of notifications for that app.

**Limitations and restrictions:**

-   The default count notification mappings must not be changed.

-   The default text notification mapping must not be changed.

-   Notification icons provided by the app and displayed on the lock screen must be monochromatic, with a white foreground color and a transparent background color.

-   After first boot, apps can only be assigned as a lock screen notification by the user; apps must not automatically use a notification slot.

-   Users can delete apps that support notifications, and they can also select alternate notification mappings.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
For more information about building an app that supports notifications on the lock screen, see the Windows developer documentation.

**To preload and specify the app that supports lock screen notifications:**

1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LockScreenNotifications"  
                         Description="Use to preload an app that supports lock screen notifications and set the app to use the 5th slot on the lock screen."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Applications>
          <Application Source=""
                       License=""
                       ProvXML="" />
        </Applications>

        <Settings Path="LockScreen">  
          <Setting Name="LockNotificationAppID" Value="" /> 
          <Setting Name="LockNotificationAppTile" Value="default" />  
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Preload the app that supports lock screen notifications by specifying these settings:

    -   Set `Source` to the path and name of the app's .xap file.

    -   Set `License` to the path and name of the app's license file.

    -   Set `ProvXML` to the path and name of the app's PROVXML file.

4.  Set the `LockNotificationAppID` setting `Value` to correspond to your app' s app ID or GUID.

5.  Replace the `LockNotificationAppTile` setting `Value` to match the **TokenID** value that was in your app manifest file. If you do not have a **TokenID** specified, set the `Value` to *default*.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image that contains this customization to a device.

2.  Go to **Settings** &gt; **Lock screen**.

3.  Scroll down and verify that your lock screen notification app now shows as the default app in fifth slot under **Choose apps to show quick status**.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
