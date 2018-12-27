---
title: Additional notification sounds
description: Partners can add up to three new notification sounds and a reminder sound. In addition, you can also specify a default notification sound for messaging, voicemails, and reminders.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a0852ef2-74e3-40f8-b859-716302391dbe


ms.date: 05/02/2017
ms.topic: article


---

# Additional notification sounds


Partners can add up to three new notification sounds and a reminder sound. In addition, you can also specify a default notification sound for messaging, voicemails, and reminders.

Alerts should have a length of 1 to 3 seconds and be as small as possible in size. They must be in .wma format, with a compression of 128 kbit/s for stereo or 64 kbit/s for mono. Partner sounds should play at an appropriate volume relative to other sounds and ringtones, and there should be minimal distortion from the device speaker, at full volume.

**Limitations and restrictions**:

-   The names of the sounds must be localized for all display languages that ship on the device.

-   Sound files must be approved by Microsoft.

-   Partners must not move, delete, or modify the notification sounds provided by Microsoft.

Partners must keep the following design considerations in mind when implementing additional notification sounds:

**File size:** Ringtone recommended maximum 150 KB; Alarm 100 KB(others as small as possible)

**Format:** .wma

**Compression:** WMA (128 kbps/stereo; 64 kbps/mono)

**Sound length:** Ringtones 5-15 seconds; Alarm 5-15 seconds; Calendar 1-3 seconds; Alerts 0.5-1.5 seconds

**Appropriate volumes:** Sounds should be appropriately balanced with the ringtones and system sounds that's part of the OS.

**Minimal distortion** from phone speaker, at full volume.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
**To add additional notification sounds**

1. Create a .dll that contains the notification sound display name. For more information on how to do this, see [Create a resource-only .dll for localized strings](create-a-resource-only-dll-for-localized-strings.md).

2. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                        Name="AdditionalNotifications"  
                        Description="Use to add additional notification sounds and set new default notification sounds for 
                                     messaging, voicemail, or calendar reminders."  
                        Owner=""  
                        OwnerType="OEM"> 
      
      <Static>  

       <Settings Path="Localization/MUI">  
         <!-- Use to add your base MUI DLL file -->
         <Asset Name="BaseDll" Source="" />

         <!-- Use to specify the language MUI packages (*.dll.mui) for the languages you are supporting and have localized strings for -->
         <Asset Name="LanguageDll/$(langid)" Source="" />
         <Asset Name="LanguageDll/$(langid)" Source="" />
         <Asset Name="LanguageDll/$(langid)" Source="" />
         <!-- Add as many as you need -->         
       </Settings>  

       <Settings Path="EventSounds">  
          <!-- Use to add up to three new notification sounds and one additional notification sound for calendar reminders -->
          <Asset Name="NotificationSounds" DisplayName="@DisplayStrings.dll,-Offset" Source="" />
          <Asset Name="NotificationSounds" DisplayName="@DisplayStrings.dll,-Offset" Source="" />
          <Asset Name="NotificationSounds" DisplayName="@DisplayStrings.dll,-Offset" Source="" />
          <Asset Name="NotificationSounds" DisplayName="@DisplayStrings.dll,-Offset" Source="" />
       </Settings>  

      </Static>

   </ImageCustomizations>
   ```

3. Specify an `Owner`.

4. Add the resource-only .dll that contains the notification sounds' display names by setting the `BaseDll` asset to point to the location of your base MUI DLL file. For example: *C:\\Path\\DisplayStrings.dll*.

5. Add the language MUI packages (\*.dll.mui) for all the languages you are supporting and have localized strings for. To do this:

   -   Set the asset's `Name` to `LanguageDll/`*$(langid)* where *$(langid)* corresponds to the language. For example: *LanguageDll/en-US*.

   -   Set the asset's `Source` to the location of the .dll.mui file for that language. For example: *C:\\Path\\en-us\\DisplayStrings.dll.mui*.

   -   Repeat the previous steps for the other languages.

       The following example shows the customization answer file entries for en-US, fr-CA, and es-MX languages:

       ```XML
       <Asset Name="LanguageDll/en-US" Source="C:\Path\en-us\DisplayStrings.dll.mui” />
       <Asset Name="LanguageDll/fr-CA" Source="C:\Path\fr-CA\DisplayStrings.dll.mui" />
       <Asset Name="LanguageDll/es-MX" Source="C:\Path\es-MX\DisplayStrings.dll.mui" />
       ```

6. Add additional notification sounds by adding a `NotificationSounds` asset. To do this:

   - Set the asset's `Name` to `NotificationSounds`.

   - Set the `DisplayName` to the name of the resource-only .dll file and specify the string offset. Replace *DisplayStrings.dll* with the name of your .dll file and replace *Offset* with the correct offset for the localized string. For example: <em>@DisplayStrings.dll,-104</em>.

   - Set `Source` to the full path to the custom notification sound on your development machine. For example: *C:\\Path\\NewVoicemailNotification.wma*.

   - Repeat the previous steps for any additional notification sounds. Partners can add up to three new notification sounds and one additional notification sound for reminders.

If you are setting the default notification sound in addition to adding other notification sound files, see the *To set a new sound for messaging, voicemail, or reminders* section.

**To set a new default notification sound for messaging, voicemail, or reminders**

1.  Create a customization answer file using the contents shown in the following code example:

    ```XML
        <Settings Path="EventSounds">
            <!-- Use to set a new default voicemail notification sound -->
            <Setting Name="DefaultVoicemailAlertSound" Value="" />

            <!-- Use to set a new default reminder sound -->
            <Setting Name="DefaultReminderAlertSound" Value="" />

            <!-- Use to set a new default messaging notification sound -->
            <Setting Name="DefaultMessagingSound" Value="" />

        </Settings>
    ```

2.  For the default notification sound that you want to configure, set the `Value` to the desired default notification sound file name.

    For example, if you only want to set `DefaultMessagingSound` to the messaging sound that you added, set the default messaging sound value to *MessagingSound.wma*.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization and multiple display languages to a mobile device.

2.  Go to the **Sounds** settings screen. Verify that all added custom notification sounds appear as expected.

3.  Go to the **Notifications & actions** screen in **Settings**. From the list, select an email account, **Messaging**, or **Phone**, and then select the **Notification sound** drop-down list to verify all added custom notification sounds for voicemail and messaging appear in the drop-down list.

4.  Verify the custom notification sound names are correct for all display languages on the device.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
