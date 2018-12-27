---
title: Default list of countries/regions
description: OEMs can select the countries/regions to exclude from the default list shown in the mobile device's Country/Region list in the Settings screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 074130F7-E5F3-4FD1-BB64-E20D016AA17D


ms.date: 05/02/2017
ms.topic: article


---

# Default list of countries/regions


OEMs can select the countries/regions to exclude from the default list shown in the mobile device's **Country/Region** list in the **Settings** screen.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DefaultRegionsList"  
                         Description="Use to specify list of countries/regions to exclude from Country/Region list."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Globalization">  
          <Setting Name="ExcludedNations" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value for `ExcludedNations` to specify the countries/regions that should not show up on the device's **Country/Region** list in the **Region** settings page.

    You can specify the value as a list of semicolon-delimited ISO-3166-1 Alpha2 character codes (no spaces) that should be excluded when enumerating all supported countries with **EnumSystemGeoID**. The entire string must not be larger than 255 characters. The value must have a maximum of 85 codes only. Note that some ISO-3166-1 ALPHA2 codes cover multiple GeoIDs.

    The value for `ExcludedNations` must follow this format: "IO;SJ;AQ;BV;CX;CC;HM;NF;MP;PN;GS;TK;WF;BL;UM"

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device.

2.  After device setup, go to the **Region** screen in **Settings**.

3.  .

4.  Look at the **Country/Region** list to verify that the countries or regions you specified in `ExcludedNations` are not showing up on the list.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
