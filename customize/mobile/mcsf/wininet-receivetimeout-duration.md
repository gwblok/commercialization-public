---
title: WinInet ReceiveTimeOut duration
description: In cases where there are issues related to network handovers, partners can increase the WinInet ReceiveTimeOut value to provide more time for the network switch to take place.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 80ff5a90-1ac4-4275-940d-a9bbc784f2a1


ms.date: 05/02/2017
ms.topic: article


---

# WinInet ReceiveTimeOut duration


In cases where there are issues related to network handovers, partners can increase the WinInet ReceiveTimeOut value to provide more time for the network switch to take place.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WinInetReceiveTimeOut"  
                         Description="Use to configure the WinInet Internet options ReceiveTimeOut value."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="WinInet/InternetSettings">  
          <Setting Name="WinInetReceiveTimeOut" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value`, in milliseconds, to a number between 30000 and 120000 (inclusive). This value is will be used as the WinInet ReceiveTimeOut value.

    The default OS value is 60000 milliseconds (60 seconds).

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator partner to fully test this customization on their network.

1.  Flash a build containing this customization to a phone with a cellular connection.

2.  Place the phone in an area with a weak field signal, for example a weak 3G field.

3.  Download a file during 2G to 3G handover.

4.  Download a file during 3G to 2G handover.

5.  Verify that the files were downloaded successfully. If not, adjust the value for `WinInetReceiveTimeOut` as needed.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
