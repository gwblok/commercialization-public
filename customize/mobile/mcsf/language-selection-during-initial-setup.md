---
title: Language selection during initial setup
description: If multiple display languages are included on the device, partners have the option of hiding the Language selection screen during setup.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: df02fcad-e3cb-49d7-ae8e-5bcdfe0a0fce


ms.date: 05/02/2017
ms.topic: article


---

# Language selection during initial setup


If multiple display languages are included on the device, partners have the option of hiding the **Language selection** screen during setup. As a result, the device will use the default specified by the OEM, and users can change the language later by using the **Time & Language** screen in **Settings**.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Specify more than one phone language for your image. For more information, see [Phone languages](phone-languages.md).

2.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LanguageSelectionScreen"  
                         Description="Use to show or hide the language selection screen during setup."
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="SetupWizard">  
          <Setting Name="ShowLanguageSelectionScreenInSetup" Value="" />  
        </Settings>

       </Static>
    </ImageCustomizations>
    ```

3.  Specify an `Owner`.

4.  Set the `Value` to either of the following:

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
    <td><p>0 or 'Hide'</p></td>
    <td><p>Hides the <strong>Language selection</strong> screen during setup.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Show'</p></td>
    <td><p>Shows the <strong>Language selection</strong> screen during setup.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization and multiple languages to a phone.

2.  At the beginning of setup, verify that the **Language selection** screen is either shown or hidden depending on the default value you specified.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
