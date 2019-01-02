---
title: Reset the audio volume limitation and warning
description: OEMs can set the device to reset the audio volume limit and show the volume level warning every time the volume level exceeds a certain permitted threshold for a certain length of time.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 802a4023-aebb-4709-b618-9cf496071166


ms.date: 05/02/2017
ms.topic: article


---

# Reset the audio volume limitation and warning


OEMs can set the device to reset the audio volume limit and show the volume level warning every time the volume level exceeds a certain permitted threshold for a certain length of time.

To reset the audio volume limit and show the volume level warning every time the volume level exceeds a certain permitted threshold for at least 20 cumulative hours, OEMs can set the **VolumeThresholdPlayTimeLimit** registry value. By default, the cumulative time limit for the audio volume limit is set to 20 hours and the OS timer that tracks the cumulative time limit is fired every 6 minutes so OEMs must set **VolumeThresholdPlayTimeLimit** to a value ≤ 19 hours and 54 minutes. When set, the volume drops back to the permitted threshold set in the [Audio volume limitation](audio-volume-limitation.md) customization if the user has been listening to music at more than the permitted volume limit and the cumulative listening time is between 19 hours, 54 minutes and 20 hours. The volume limit warning will also reappear.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create the MCSF policy setting that corresponds to the following registry key:

    ```
    $(HKLM.MICROSOFT)\ZMediaQ\VolumeLimit\VolumeThresholdPlayTimeLimit
    Type:  REG_DWORD
    Value:  000117D8
    ```

    > [!NOTE]
    > Set **Value** to a hexadecimal value that corresponds to 19 hours and 54 minutes or less. In the above example, the value 0x00117D8 corresponds to 71640 seconds or 19 hours and 54 minutes.

    For more information about MCSF, see [Managed Centralized Settings Framework (MCSF)](managed-centralized-settings-framework-mcsf.md). The following code example shows an MCSF policy setting for the **VolumeThresholdPlayTimeLimit** registry value.

    ```XML
             <SettingsGroup Path="VolumeLimit">
                <Setting Name="VolumeThresholdPlayTimeLimit" Description="Resets the audio volume limit and shows the volume level warning
                              every time the volume exceeds the VolumeLimit threshold for at least 20 cumulative hours.">
                  <RegistrySource Type="REG_DWORD" Path="HKEY_LOCAL_MACHINE\Software\Microsoft\ZMediaQ\VolumeLimit\VolumeThresholdPlayTimeLimit" />
                </Setting>
             </SettingsGroup>
    ```

2.  Add the policy setting in the previous step to a .pkg.xml file. The following code example shows the MCSF policy setting within the .pkg.xml file.

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <Package xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"
      Owner=""
      Component=""
      SubComponent=""
      OwnerType="OEM"
      ReleaseType="">
       <Components>
             <SettingsGroup Path="VolumeLimit">
                <Setting Name="VolumeThresholdPlayTimeLimit" Description="Resets the audio volume limit and shows the volume level warning
                              every time the volume exceeds the VolumeLimit threshold for at least 20 cumulative hours.">
                  <RegistrySource Type="REG_DWORD" Path="HKEY_LOCAL_MACHINE\Software\Microsoft\ZMediaQ\VolumeLimit\VolumeThresholdPlayTimeLimit" />
                </Setting>
             </SettingsGroup>
       </Components>
    </Package>
    ```

    In this example, provide values for the **Owner**, **Component**, **SubComponent**, and **ReleaseType** attributes.

3.  Use the .pkg.xml file that contains your MCSF policy setting to generate a package (or .spkg file) that you can add to your OS image. 

4.  After you've created the .spkg, define the specific types of image builds that you want to contain the package.

    For example, the following code snippet shows a sample OEM feature manifest (FM) file that may contain the .spkg that includes the customization:

    ```XML
    <?xml version="1.0" encoding="utf-8"?>  
    <FeatureManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate">  
    <!--  Sample FM File -->
      <Features>  
        <OEM>  
          <PackageFile Path="SourceDirectory" Name="OEMName.SoundCustomizations.VolumeThresholdPlayTimeLimit.spkg">  
            <FeatureIDs>  
              <FeatureID>VOLUME_THRESHOLD_PLAY_TIME_LIMIT</FeatureID>  
            </FeatureIDs>  
          </PackageFile>  
        </OEM>  
      </Features>  
    </FeatureManifest>  
    ```

    In this example, replace *SourceDirectory* with the location that contains the .spkg that you created in Step 3. Also, replace the example *OEMName.SoundCustomizations.VolumeThresholdPlayTimeLimit.spkg* with the name of the .spkg file.

5.  Once you've defined the feature, modify your OEMInput.xml file to add a **Features** element (if one doesn't already exist), add a new **OEM** child element (if one doesn't already exist), and add a new **Feature** entry with the name of the feature that you just defined.

    For example, the OEMInput.xml entry for the example VOLUME\_THRESHOLD\_PLAY\_TIME\_LIMIT feature may look like the following:

    ```XML
      <Features>
        <OEM>
          <Feature>VOLUME_THRESHOLD_PLAY_TIME_LIMIT</Feature>
        </OEM>
      </Features>
    ```

    For more information, see [OEMInput file contents](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/oeminput-file-contents).

6.  Build the OS image. For more information, see *Using ImgGen.cmd to generate an image* in [Building a mobile image using ImgGen.cmd](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/building-a-phone-image-using-imggencmd).

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build that contains this customization to a device.

2.  Set up your device and load music on the device.

3.  Use the device and headset to play and listen to music. Turn up the volume above the limit that you set for the **VolumeLimit** setting in [Audio volume limitation](audio-volume-limitation.md).

    Continue to listen to music for 20 or more hours.

4.  If you set **VolumeThresholdPlayTimeLimit** to a hexadecimal value that corresponds to 19 hours and 54 minutes (or less), verify that the volume level is reset and the volume warning is shown before you reach 20 cumulative hours of playing music with the volume set above the **VolumeLimit**.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
