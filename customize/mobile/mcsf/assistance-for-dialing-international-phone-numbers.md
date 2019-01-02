---
title: Assistance for dialing international phone numbers
description: Partners can turn off the international assist feature that helps users with the country codes needed for dialing international phone numbers.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 95f93ca3-0481-46bd-93a0-a63380f87bca


ms.date: 05/02/2017
ms.topic: article


---

# Assistance for dialing international phone numbers


Partners can turn off the international assist feature that helps users with the country codes needed for dialing international phone numbers. This customization is recommended when the device will be sold in a country or region that has multiple IDD (country exit code) values.

If the country or region has multiple IDD values but a default is set, international assist will occasionally be successful. The following lists show the countries and regions that are affected for placing or receiving calls.

-   Multiple IDD values, No Default (rarely successful):

    Belize, Brazil, Cambodia, Columbia, Indonesia, Israel, Korea, Maldives, Mauritius, Mongolia, New Caledonia, Singapore, Solomon Islands, Taiwan, Thailand, Uganda, Uruguay

-   Multiple IDD values, default set (occasionally successful):

    Australia, Costa Rica, Finland, Guatemala

If the international assist feature is turned off, it is also possible to override the MNC and MCC used for SMS. For more information, see [International assisted dialing for SMS](international-assisted-dialing-for-sms.md).

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="AssistedDialSetting"  
                         Description="Use to set the default state of the international assist feature that helps users with country codes needed for dialing international phone numbers."  
                         Owner=""  
                         OwnerType="OEM"> 
    <Static>
        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="AssistedDialSetting" Value="" />      
        </Settings>  
    </Static>
    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `AssistedDialSetting` to one of the following values:

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
    <td><p>Turns off the international assist feature by default</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or True</p></td>
    <td><p>Turns on the international assist feature by default</p></td>
    </tr>
    </tbody>
    </table>



~~~
By default, the international assist feature is turned off.
~~~

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Go to the **Phone** settings screen.

3.  Verify whether the **International assist** option is visible, and if so, whether it is turned on or off.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
