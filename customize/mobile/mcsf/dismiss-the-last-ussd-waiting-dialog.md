---
title: Dismiss the last USSD waiting dialog
description: Dismiss the last USSD waiting dialog in the case where there is a sequence of USSD or SIM app dialogs.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 829b34c7-f36c-44e3-9770-4584013847e7


ms.date: 05/02/2017
ms.topic: article


---
# Dismiss the last USSD waiting dialog

Dismiss the last USSD waiting dialog in the case where there is a sequence of USSD or SIM app dialogs.

This customization affects the behavior of USSD dialog sequencing. It dismisses the last **Waiting…** dialog in the case where there is a sequence of USSD or SIM app dialogs. OEMs may need to configure this customization in cases where there is a sequence of two or more SIM app dialogs and where the OS might display a **Waiting…** dialog indefinitely and the dialog can only dismissed when the user taps **Cancel**.

<a href="" id="constraints---none"></a>**Constraints:** None
This customization supports: **per-IMSI** value

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="AutoDismissUssdWaitingDialog"
                        Description="Use to dismiss the last 'Waiting...' dialog in cases where there is a sequence of USSD or SIM app dialogs"."
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

       <Settings Path="Phone/PerSimSettings/$(__IMSI)">
         <Setting Name="AutoDismissUssdWaitingDialog" Value="" />
       </Settings>

     </Variant>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. For the **per-IMSI** case:

   1. Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.
   1. Define settings for a **Variant**, which are applied if the associated target's conditions are met.

1. Set `AutoDismissUssdWaitingDialog` to one of the following values:

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
    <td><p>The last <strong>Waiting…</strong> dialog won't be dismissed until the user cancels to dismiss the dialog. This may be confusing in some cases and can make the dialog appear frozen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>The last <strong>Waiting…</strong> dialog will be automatically dismissed when the sequence of USSD or SIM app dialogs completes.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    </tbody>
    </table>

## Testing

Work with your mobile operator to fully test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
