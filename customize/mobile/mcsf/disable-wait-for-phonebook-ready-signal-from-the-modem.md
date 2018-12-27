---
title: Disable wait for phonebook ready signal from the modem
description: FDN SIM contacts syncs from the SIM during device boot.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3872329f-80d2-460d-b7af-51e192200631


ms.date: 05/02/2017
ms.topic: article


---

# Disable wait for phonebook ready signal from the modem


FDN SIM contacts syncs from the SIM during device boot. By default, this component waits until the phonebook ready signal is received from the modem and then it verifies whether FDN contact management is enabled on the SIM. If needed, OEMs can disable the wait for the phonebook ready signal.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CheckFDNStateAfterPhonebookReady"  
                         Description="Use to disable the wait for the phonebook ready signal from the modem."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="People/SIMContactManagement">  
          <Setting Name="CheckFDNStateAfterPhonebookReady" Value="" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `CheckFDNStateAfterPhonebookReady` to one of the following values:

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
    <td><p>Disables the wait until the phonebook ready signal from the modem is received.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Waits for the phonebook ready signal from the modem before verifying whether FDN contact management is enabled on the SIM.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device with a SIM that has FDN enabled.

2.  Go through the setup process and then enter the PIN to unlock the SIM when prompted and wait for the Start screen to appear.

3.  Go to the **People** Hub and verify that FDN contacts are visible.

4.  Go to the **Settings** &gt; **phone** &gt; **SIM** settings screen and verify that FDN is shown as On.

5.  Additionally, you can test SIMs from two operators and verify that:

    -   Both SIM cards show FDN contacts correctly.

    -   Enabling and disabling FDN works.

    -   Operator voice calls are allowed or blocked correctly based on the FDN status and FDN contacts list.

    -   Adding and deleting contacts in the FDN phonebook works.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
