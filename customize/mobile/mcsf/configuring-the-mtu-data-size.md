---
title: Configuring the MTU data size
description: For TCP, the default maximum transmission unit (MTU) is set to 1500 bytes, and the maximum segment size (MSS) is 1460 bytes.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0B84B86E-7917-4C52-B26A-AB02A83FDFC9


ms.date: 05/02/2017
ms.topic: article


---

# Configuring the MTU data size


For TCP, the default maximum transmission unit (MTU) is set to 1500 bytes, and the maximum segment size (MSS) is 1460 bytes. In general, this value should not be changed, as the user experience will degrade if low values are set. However, if the MSS does not meet the requirements of the mobile operator network, OEMs can customize it by setting the MTU data size.

**Note**  This customization configures the MTU so the size should be set to the required MSS size plus 40 bytes.

 

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MTUDataSizeSettings"  
                         Description="Use to configure the MTU data size or roaming MTU data size."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  

        <Settings Path="CellCore/PerDevice/External/ImageOnly">  
          <Setting Name="MTU/MTUDataSize" Value="" />  
          <Setting Name="MTU/RoamingMTUDataSize" Value="" />  
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  To change the default MTU data size, set the value for the `MTU/MTUDataSize` setting.

4.  To change the default roaming MTU data size, set the value for the `MTU/RoamingMTUDataSize` setting.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
