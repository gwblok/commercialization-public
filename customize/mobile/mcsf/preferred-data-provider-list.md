---
title: Preferred data provider list
description: For mobile operators that require it, OEMs can set a list of MCC/MNC pairs for the purchase order (PO) carrier or primary operator so that it can be set as the default data line for phones that have a dual SIM.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3c991ec4-2472-4890-baa7-7fa473367b0b


ms.date: 05/02/2017
ms.topic: article


---

# Preferred data provider list


For mobile operators that require it, OEMs can set a list of MCC/MNC pairs for the purchase order (PO) carrier or primary operator so that it can be set as the default data line for phones that have a dual SIM.

When the PO SIM is inserted into the phone, the OS picks the PO SIM as the data line and shows a notification to the user that the SIM has been selected for internet data. If two PO SIMs are inserted, the OS will choose the first PO SIM that was detected as the default data line and the mobile operator action required dialogue (ARD) is shown. If two non-PO SIMs are inserted, the user is prompted to choose the SIM to use as the default data line.

**Note**  
OEMs should not set this customization unless required by the mobile operator.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="PreferredDataProviderList"  
                         Description="Use to specify the list of preferred mobile operators' MCC and MNC 
                                      information to use for data connections."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="CellCore/PerDevice/General">  
          <Setting Name="PreferredDataProviderList" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To enumerate the MCC/MNC value pairs to use for data connections, set the value for `PreferredDataProviderList`. The value must be a comma-separated list of preferred MCC:MNC values. For example, the value can be *301:026,310:030* and so on.

<a href="" id="testing-"></a>**Testing:**  
1.  Work with your mobile operator to obtain the list of preferred MCC and MNC values for data connections.

2.  Flash the build containing this customization to a dual SIM phone.

3.  Insert the PO SIM into the phone. Verify that the OS picks the PO SIM as the default data line and shows a notification that the SIM has been selected for Internet data.

4.  Insert two PO SIMs. Verify that the OS chooses the first PO SIM that was detected as the default data line and the mobile operator action required dialogue (ARD) is shown.

5.  Insert two non-PO SIMs. Verify that you can see a prompt to choose the SIM to use as the default data line.

6.  Verify that you can change the default SIM by going to the **Cellular+SIM** settings screen and selecting a different SIM to use as the default data line.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
