---
title: Configure DTMF tones
description: Partners can configure DTMF tone settings, including the duration, the pause between DTMF digits, the UX option to toggle between long and short DTMF tones, and can enable long DTMF tones when a user long-presses the dialpad.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d5ddfb83-3706-4e37-8d09-e83d348a8c94


ms.date: 05/02/2017
ms.topic: article


---
# Configure DTMF tones

Partners can configure the following DTMF tone settings when VoLTE calls are supported:

1. Duration of the DTMF tones, and the delay, or pause, between DTMF digits.
1. Enable UX option to switch between long and short DTMF tones.
1. Enable long DTMF tones if the user presses a dialpad key for an extended period.

## Configure duration of DTMF tones, and delay between digits

<a href="" id="constraints---none"></a>**Constraints:** None
This customization supports: **per-IMSI** value

### Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="DTMFTones"
                        Description="Use to configure settings for DTMF tones."
                        Owner=""
                        OwnerType="OEM">

       <Settings Path="CellCore/PerDevice/General">
         <Setting Name="DTMFOnTime" Value="" />
         <Setting Name="DTMFOffTime" Value="" />
       </Settings>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.

1. To specify the length of time, in milliseconds, to generate the DTMF tone, set `DTMFOnTime` to a value between 64 and 1000 (inclusive). For example, a value of 160 specifies 0.16 second.
1. To specify the length of time, in milliseconds, to pause between DTMF digits, set `DTMFOffTime` to a value between 64 and 1000 (inclusive). For example, a value of 120 specifies 0.12 second.

### Testing

Work with your mobile operator to fully test this customization on their network.

1. Flash the build containing this customization to a phone that has VoLTE enabled.
1. Make a VoLTE call to a service where DTMF tones can be used.
1. Verify that DTMF tones are recognized correctly. Depending on the values you specified, verify the duration of the DTMF tone and the delay between DTMF digits.

## Enable UX option to toggle between short and long DTMF tones

Partners can make a user option visible that makes it possible to toggle between short and long DTMF tones.

By default, the user option for toggling between short and long tones is hidden on GSM phones and visible for CDMA phones.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly

### Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="ShowLongTones"
                        Description="Use to make the user option for toggling between short and long tones visible to users."
                        Owner=""
                        OwnerType="OEM">
   <Static>
       <Settings Path="Phone/PhoneSettings">
         <Setting Name="ShowLongTones" Value="" />
       </Settings>
   </Static>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Set `ShowLongTones` to one of the following values:

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
   <td><p>0 or False</p></td>
   <td><p>Hides the user option to make it possible for users to toggle between short and long tones.</p></td>
   </tr>
   <tr class="even">
   <td><p>1 or True</p></td>
   <td><p>Shows the user option.</p></td>
   </tr>
   </tbody>
   </table>

## Enable long DTMF tones on long keypress

OEMs can enable long DTMF tones if the user presses a dialpad key for an extended period.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly

### Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="ContinuousDTMFEnabled"
                        Description="Use to enable long DTMF tones if the user presses a dialpad key for an extended period."
                        Owner=""
                        OwnerType="OEM">
     <Static>
       <Settings Path="Phone/PhoneSettings">
         <Setting Name="ContinuousDTMFEnabled" Value="" />
       </Settings>
     </Static>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Set `ContinuousDTMFEnabled` to one of the following values:

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
   <td><p>0 or 'False'</p></td>
   <td><p>Fixed length (burst mode) DTMF tones are emitted.</p></td>
   </tr>
   <tr class="even">
   <td><p>1 or 'True'</p></td>
   <td><p>DTMF tones will persist as long as the user presses a corresponding dialpad key.</p></td>
   </tr>
   </tbody>
   </table>

### Testing

1. Flash the build that contains this customization to a phone.
1. Test this customization on both VoLTE and non-VoLTE phone calls.
   * If enabled, DTMF tones will last as long as the key is being pressed.
   * If disabled, DTMF tones will be of fixed length.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
