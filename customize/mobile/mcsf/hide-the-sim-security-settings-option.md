---
title: Hide the SIM security settings option
description: OEMs can hide the SIM security settings option.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 80edbbce-5a6c-4dae-a5f2-68f7fff07e29


ms.date: 05/02/2017
ms.topic: article


---

# Hide the SIM security settings option


OEMs can hide the **SIM security** settings option.

By default, the is visible when you go to the **Settings** &gt; **applications** &gt; **phone** screen. To meet certain mobile operator requirements or to provide a better user experience (including scenarios where a device contains a brand new SIM that doesn't require a security PIN), OEMs can hide this settings option.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HideSIMSecurityUI"  
                         Description="Use to hide the 'SIM security' settings option from the Phone settings screen."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="HideSIMSecurityUI" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `HideSIMSecurityUI` setting to one of the following values:

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
    <td><p>Show the <strong>SIM security</strong> settings option in the <strong>Settings</strong> &gt; <strong>applications</strong> &gt; <strong>phone</strong> screen.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Hide the <strong>SIM security</strong> settings option in the <strong>Settings</strong> &gt; <strong>applications</strong> &gt; <strong>phone</strong> screen.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator partner to test this customization on their network.

1.  Flash the build containing this customization to a device that has a brand new SIM that doesn't require a security PIN.

2.  Set up the device.

3.  If you set `HideSIMSecurityUI` to 1 or 'True', go to the **Phone** settings screen and verify that the **SIM security** settings option is not visible.

4.  If you set `HideSIMSecurityUI` to 0 or 'False' or you did not change the default OS value, go to the **Phone** settings screen and verify that the **SIM security** settings option is visible.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
