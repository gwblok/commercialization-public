---
title: Sort order for contacts
description: OEMs can use this customization to set the list of contacts displayed in the People Hub to be organized by last name instead of first name or first name instead of last name.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c6735ee8-c87d-4351-bfac-be5fcfcdd236


ms.date: 05/02/2017
ms.topic: article


---

# Sort order for contacts


OEMs can use this customization to set the list of contacts displayed in the People Hub to be organized by last name instead of first name or first name instead of last name. It is also possible to change the display format of contact names to appear as “First name Last name” or “Last name First name” for markets that use more formal nomenclature.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ContactSortSettings"  
                         Description="Use to set the sorting and display setting of the user's contacts"  
                         Owner=""  
                         OwnerType="OEM"> 
      <Static>  
        <Settings Path="People/SortAndDisplaySettings">
          <Setting Name="SortBy" Value="" />
          <Setting Name="DisplayBy" Value="" />      
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `SortBy` Value to one of the following values:

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
    <td><p>[Sort1] or FirstLast</p></td>
    <td><p>Sorts the contacts in the People Hub by their first name.</p></td>
    </tr>
    <tr class="even">
    <td><p>[Sort2] or LastFirst</p></td>
    <td><p>Sorts the contacts in the People Hub by their last name.</p></td>
    </tr>
    </tbody>
    </table>

     

4.  Set the `DisplayBy` Value to one of the following values:

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
    <td><p>[Sort1] or FirstLast</p></td>
    <td><p>Displays the contacts in the People Hub in the format: “First name Last name”</p></td>
    </tr>
    <tr class="even">
    <td><p>[Sort2] or LastFirst</p></td>
    <td><p>Displays the contacts in the People Hub in the format: “Last name First name”.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Go to the **People** settings screen. Verify that the **Sort list by** option is set to **Last name**, and that the **Display names by** option is set to **Last, First**.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
