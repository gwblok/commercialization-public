---
title: Customize the SIM toolkit
description: OEMs can change the display duration for certain SIM toolkit UI dialogs or messages if the default values do not meet the requirements of the mobile operator.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 171035E9-8454-4A54-B833-7E918C91DBE4


ms.date: 05/02/2017
ms.topic: article


---
# Customize the SIM toolkit

OEMs can change the display duration for certain SIM toolkit UI dialogs or messages if the default values do not meet the requirements of the mobile operator.

The default display times for SIM toolkit commands are as follows:

* GET INPUT: 120 seconds
* DISPLAY TEXT: 60 seconds
* SELECT ITEM: 60 seconds
* GET INKEY: 60 seconds

OEMs can modify the values for the following settings.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><code>UIDefaultDuration</code></p></td>
<td><p>Specifies the default time, in milliseconds, that the DISPLAY TEXT, GET INKEY, PLAY TONE, or SELECT ITEM dialog should be displayed.</p>
<p>The default value is 60000 milliseconds (60 seconds). The valid value range is 1-120000.</p></td>
</tr>
<tr class="even">
<td><p><code>UIGetInputDuration</code></p></td>
<td><p>Specifies the default time, in milliseconds, that the GET INPUT dialog should be displayed.</p>
<p>The default value is 120000 milliseconds (120 seconds). The valid value range is 1-120000.</p></td>
</tr>
</tbody>
</table>

To customize these settings using MCSF, see the next section. If you're using Windows provisioning, use Windows Configuration Designer to customize the settings or write your own Windows provisioning answer file. Regardless of the framework that you use, you must determine if you need to use the per-device or per-IMSI setting.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="SIMToolkitCustomization"
                        Description="Use to modify certain SIM toolkit UI dialogs and messages."
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

   <!-- Use for the per-IMSI case -->
       <Settings Path="CellCore/PerIMSI/$(__IMSI)/UTK">
         <Setting Name="UIDefaultDuration" Value="" />
         <Setting Name="UIGetInputDuration" Value="" />
       </Settings>  

   <!-- Use for the per-device case -->
       <Settings Path="CellCore/PerDevice/UTK">
         <Setting Name="UIDefaultDuration" Value="" />
         <Setting Name="UIGetInputDuration" Value="" />
       </Settings>

     </Variant>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.
1. Define settings for a **Variant**, which are applied if the associated target's conditions are met.
1. Set the values for `UIDefaultDuration` and `UIGetInputDuration`.

## Testing

1. Flash the build containing this customization to a phone.
1. Go to the **Cellular & SIM** &gt; **Advanced options** settings screen to start the SIM toolkit UI app.
1. Verify that the duration that the UI dialogs and messages are displayed match the default values that you've set.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
