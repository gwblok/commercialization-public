---
title: Authentication for Wi-Fi hotspot settings
description: When mobile devices connect to a Wi-Fi hotspot that uses a captive portal, the web browser is automatically opened so that the user can sign in.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e113ac19-261c-4796-b586-6ea64397b05b


ms.date: 05/02/2017
ms.topic: article


---

# Authentication for Wi-Fi hotspot settings


When mobile devices connect to a Wi-Fi hotspot that uses a captive portal, the web browser is automatically opened so that the user can sign in. Until this authentication process is completed, the Wi-Fi hotspot connection is not available for applications and services running on the device. As a result, applications provided by mobile operators or third party vendors to authenticate the Wi-Fi hotspot settings will not work.

To suppress the launch of the browser and enable this type of application to run as expected, OEMs must register the SSID of one or more networks. These networks will be available immediately when the connection is established.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HijackedIgnoreList"  
                         Description="Use specify a list of captive portal SSIDs for which browser should not be launched automatically."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="WiFi/Config">  
          <Setting Name="HijackedIgnoreList" Value="" />  
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `HijackedIgnoreList` value to the set list of captive portal SSIDs for which the browser should not be launched automatically. For example, *ContosoWiFi;FabrikamWiFi;ContosoFabrikamWiFi* and so on.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device.

2.  Connect to a Wi-Fi network that uses one of the registered SSIDs.

3.  Verify the browser does not launch and the network is available immediately.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
