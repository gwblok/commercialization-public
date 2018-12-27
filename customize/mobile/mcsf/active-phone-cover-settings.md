---
title: Active phone cover settings
description: OEMs can create and register an active phone cover app, which allows partners to create a user experience with their mobile device cover accessories. This app must be preloaded on the phone as a Settings/CPL application.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2b926f01-d04a-4266-94c2-134efc795115


ms.date: 05/02/2017
ms.topic: article


---

# Active phone cover settings


OEMs can create and register an active phone cover app, which allows partners to create a user experience with their mobile device cover accessories. This app must be preloaded on the phone as a Settings/CPL application.

OEMs can then enable the app to be launched when the active phone cover is closed and specify the default setting for the lock screen's auto unlock setting, which determines if the lock screen is automatically lifted when the user opens the cover.

**Limitations and restrictions:**

When the OS receives a notification that the cover state has been set to Closed:

-   The OS locks the device.

-   The OS uses the **AUMID** setting to launch the active phone cover app. The app is launched in the foreground, above the lock screen, and the app is rendered at the top of the z-order.

When the OS receives a notification that the cover state has been set to Opened:

-   The OS terminates the active phone cover app and shows the default lock experience.

-   If the user opens the cover and the **AutoUnlock** setting is set to 1, the OS automatically lifts the lock screen and tries to unlock the device. If the device does not have a password lock, the OS unlocks the device. Otherwise, the OS prompts the user for their password.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SmartCover"  
                         Description="Use to preload and configure your active phone cover app."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <!-- Preload the phone cover app. Specify the source, license, and ProvXML files. -->
        <Applications>
          <Application Source=""
                       License=""
                       ProvXML="" />
        </Applications>

        <Settings Path="Shell/SmartCover">  
          <Setting Name="AUMID" Value="" />  
          <Setting Name="AutoUnlock" Value="" />  
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To preload the active phone cover app, add an **Applications** parent element and add an **Application** child element to correspond to the active phone cover app that you are preloading. For the **Application**, specify the values for the following settings:

    -   `Source` – Set to the path and name of the app to preload.

    -   `License` – Set to the path and name of the app license file.

    -   `ProvXML` – Set to the path and name of the provisioning XML file that corresponds to the app.

4.  To enable the app to be launched when the cover is closed, set the value of `AUMID` to your app's Application User Model ID (AUMID). To identify the AUMID, follow the information in this [Microsoft Web site](http://go.microsoft.com/fwlink/p/?LinkId=404220). The value must be in the format similar to this example: *SmartCoverApp\_&lt;PublisherID&gt;!App*.

5.  To specify the default setting for the lock screen's auto unlock setting and determine if the lock screen is automatically lifted when the user opens the active phone cover, set `AutoUnlock` to one of the following values:

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
    <td><p>The lock screen is not lifted when the user opens the active phone cover.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>The lock screen is automatically lifted when the user opens the active phone cover.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone.

2.  Set up the phone and then go to **Settings** screen. Verify that the active phone cover app appears in the Settings CPL.

3.  With the active phone cover attached to the phone, close the cover. Verify that the active phone cover app is launched successfully once the cover is closed.

4.  Depending on the value you specified for the `AutoUnlock` setting, verify whether the lock screen is automatically lifted when you open the active phone cover.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
