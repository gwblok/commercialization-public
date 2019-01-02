---
title: Use HD audio codec for call branding
description: OEMs can customize call progress branding when a call is made using a specific audio codec.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: F38B7E1E-0CED-4644-B652-E70D3BFE69FD


ms.date: 05/02/2017
ms.topic: article


---

# Use HD audio codec for call branding


OEMs can customize call progress branding when a call is made using a specific audio codec.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
     <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableSupplementaryServiceEraseToDeactivateOverride" Description=”Call progress branding”
                         Owner=""  
                         OwnerType="OEM"> 

      <!-- Define the Targets --> 
      <Targets>
         <Target Id="">
            <TargetState>
               <Condition Name="" Value="" />
               <Condition Name="" Value="" />
            </TargetState>
         </Target>
      </Targets>

      <Static>
        <Settings Path="Multivariant">
          <Setting Name="Enable" Value="1" />
        </Settings>
        <Settings Path="AutoDataConfig">
          <Setting Name="Enable" Value="0" />
        </Settings>
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>
         <Settings Path="Phone/PerSimSettings/$(__IMSI)/HDAudio">  
          <Setting Name="" Value="" /> <!-- Use to identify codec and string -->
         </Settings>   
      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  For the per-IMSI case:

    1.  Define Targets or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define Targets or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  In the table below, identify the `Setting Name` that corresponds to your HD audio codec, and set that as `Setting Name`. Then, set `value` to the text string you want to use for call progress branding. For example, if you are using the EVRC audio codec, and you would like to display the text "EVRC" when using that codec, you would enter EVRCAudioQualityString in `Setting Name`, and EVRC in `Value. `

    **Note:** Text strings can be a maximum of 10 characters.

    | Setting name               | Value           | Description                                                     |
    |----------------------------|-----------------|-----------------------------------------------------------------|
    | EVRCAudioQualityString     | Any text string | Call progress branding for calls using the EVRC audio codec     |
    | EVRCBAudioQualityString    | Any text string | Call progress branding for calls using the EVRCB audio codec    |
    | EVRCNWAudioQualityString   | Any text string | Call progress branding for calls using the EVRCNW audio codec   |
    | EVRCWBAudioQualityString   | Any text string | Call progress branding for calls using the EVRCWB audio codec   |
    | EVSFBAudioQualityString    | Any text string | Call progress branding for calls using the EVSFB audio codec    |
    | EVSNBAudioQualityString    | Any text string | Call progress branding for calls using the EVSNB audio codec    |
    | EVSSWBAudioQualityString   | Any text string | Call progress branding for calls using the EVSSWB audio codec   |
    | EVSWBAudioQualityString    | Any text string | Call progress branding for calls using the EVSWB audio codec    |
    | GSMEFRAudioQualityString   | Any text string | Call progress branding for calls using the GSMEFR audio codec   |
    | GSMFRAudioQualityString    | Any text string | Call progress branding for calls using the GSMFR audio codec    |
    | GSMFRAudioQualityString    | Any text string | Call progress branding for calls using the GSMFR audio codec    |
    | QCELP13KAudioQualityString | Any text string | Call progress branding for calls using the QCELP13K audio codec |

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  Make a phone call that uses HD audio.

3.  Verify that the call progress branding is displayed during the phone call.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
