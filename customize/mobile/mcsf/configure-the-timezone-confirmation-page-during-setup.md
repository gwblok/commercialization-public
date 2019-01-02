---
title: Configure the timezone confirmation page during setup
description: Use to allow users to change the timezone and region during device setup.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 13f0314b-ac73-4807-a1d9-1d9a60e47756


ms.date: 05/02/2017
ms.topic: article


---

# Configure the timezone confirmation page during setup


Use to allow users to change the timezone and region during device setup.

By default, the OS shows the timezone confirmation page during initial device setup after the device receives the Network Identity and Time Zone (NITZ) information. This page allows users to change the timezone and region during setup. To meet requirements from some mobile operators, OEMs can hide this page.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableNITZTimeDateConfirmation"  
                         Description="Use to configure the timezone confirmation page during initial device setup."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="SetupWizard">  
          <Setting Name="EnableNITZTimeDateConfirmation" Value="" />  
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `EnableNITZTimeDateConfirmation` to one of the following values:

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
    <td><p>0 or 'Disable'</p></td>
    <td><p>Hides the timezone confirmation page during setup.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enable'</p></td>
    <td><p>Shows the timezone confirmation page during setup.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device capable of receiving NITZ information.

2.  During the initial device setup process, verify that the timezone confirmation page is either hidden or shown in the UI depending on the value that you set for `EnableNITZTimeDateConfirmation`.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
