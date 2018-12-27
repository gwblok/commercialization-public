---
title: Use OK for USSD dialogs
description: To meet certain market requirements or user expectations, OEMs can change the button label in USSD dialogs from Close (the default) to OK.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7b18f01e-dd3a-46b4-9016-7fb5c0da7aa8


ms.date: 05/02/2017
ms.topic: article


---

# Use OK for USSD dialogs


To meet certain market requirements or user expectations, OEMs can change the button label in USSD dialogs from **Close** (the default) to **OK**.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="UseOKForUssdDialogs"  
                         Description="Use to change the button label in USSD dialogs from 'Close' to 'OK'."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="UseOKForUssdDialogs" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Change the button label in the USSD dialog by setting `UseOKForUssdDialogs` to one of the following values:

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
    <td><p>USSD success and failure dialogs have a single button to close the dialog labeled <strong>Close</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>USSD success and failure dialogs have a single button to close the dialog labeled <strong>OK</strong></p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone that has a UICC.

2.  Open the **Phone** app and tap the keypad button.

3.  Use several USSD codes and strings to bring up a USSD success dialog and a USSD failure dialog.

4.  Verify that the button label in the dialog shows **OK**.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
