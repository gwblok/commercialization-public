---
title: Sort order for contacts override
description: OEMs can customize the default values for people sort and display settings as documented in the Sort order for contacts customization.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f71ed846-9547-4f24-bd53-d44d255cbf5d


ms.date: 05/02/2017
ms.topic: article


---

# Sort order for contacts override


OEMs can customize the default values for people sort and display settings as documented in the [Sort order for contacts](sort-order-for-contacts.md) customization. However, these settings may be overridden by the defaults for the user’s current locale unless the OEM sets an additional override registry key.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
      <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="OEMOverridesSortDisplay"  
                         Description="Use to prevent OEM values for people sort and display settings from being overridden by user's current locale."  
                         Owner=""  
                         OwnerType="OEM">
     <Static>  
        <Settings Path="People/SortAndDisplaySettings">  
          <Setting Name="OEMOverridesSortDisplay" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `OEMOverridesSortDisplay` value to 1 or 0x1 to prevent the OEM values for people sort and display settings from being overridden.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Go to the **People** settings screen.

3.  Verify that the **Sort list by** and the **Display names by** option is set to the values you specified in the [Sort order for contacts](sort-order-for-contacts.md) customization.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
