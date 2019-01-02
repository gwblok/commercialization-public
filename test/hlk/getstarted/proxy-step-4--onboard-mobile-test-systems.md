---
title: Step 4 Onboard Mobile Test systems
description: Step 4 Onboard Mobile Test systems
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3CEA61AA-5625-4F1F-84ED-69ED726BB74F


ms.date: 10/15/2017
ms.topic: article


---

# Step 4: Onboard Mobile/IoT Test systems


After you install the Windows Hardware Lab Kit (Windows HLK) on the Controller system, and the Windows HLK Proxy Client on the Proxy system, you are ready to add mobile/IoT test systems to the environment.

## <span id="Known_Issues"></span><span id="known_issues"></span><span id="KNOWN_ISSUES"></span>Known Issues


| Issue                                                 | Workaround         |
|------------------------------------------------------|--------------------|
| Device name reported in HLK as **Windows Phone** instead of the actual device name. | Reboot the device. |

 

## <span id="Onboarding_USB_connected_devices"></span><span id="onboarding_usb_connected_devices"></span><span id="ONBOARDING_USB_CONNECTED_DEVICES"></span>Onboarding USB connected devices


1.  On the Proxy system, launch an elevated command prompt window.
2.  Navigate to %ProgramFiles(x86)%\\WTTMobile\\Tools\\
3.  Get the DeviceGUID for the connected device:
    1.  Put the device in flashing mode.
    2.  From the elevated command prompt, run the following command:

        ``` syntax
        ffutool.exe -list
        ```

        >[!NOTE]
        >FFUTool.exe is included in the HLK at \\\\<ControllerName>\HLKInstall\ProxyClient\FfuTool.
        >Copy the entire contents of this directory to your proxy server.
        >
        >For more information on HLK mobile testing tools and utilities, see [HLK Mobile Testing Tools and Utilities](../user/hlk-mobile-testing-tools-and-utilities.md)
        >
        >FFUTool.exe can be also installed with the ADK, by selecting the Imaging and Configuration Designer option during kit installation. 
        >For more information on the ADK, see [Download the Windows ADK](https://developer.microsoft.com/en-us/windows/hardware/windows-assessment-deployment-kit)
        >

4.  Run the following command from the elevated command prompt to put the device into mass storage mode:

    ``` syntax
    ffutool -MassStorage
    ```

5.  Unplug the device from the proxy system, then plug it back in. It will then be assigned a drive letter on the Proxy system.  Use this as the &lt;device drive&gt; in the next step.
6.  Enable USB EEM protocol on boot options. From an elevated command prompt, run the following command: 

    ``` syntax
    BCDEdit /store <device drive>:\EFIESP\efi\Microsoft\Boot\BCD /set {default} loadoptions "EEM"
    ```

    Example:

    `BCDEdit /store G:\EFIESP\efi\Microsoft\Boot\BCD /set {default} loadoptions "EEM"`

7.  Restart the device (if the image installed on the DUT is a lab or a health image, put the device in flashing mode).
8.  To onboard the device, from the elevated command prompt, run the following command:

    ``` syntax
    KitsDeviceDetector.exe /Physical:Fake_PC.dll /DeviceName:<DeviceName> /DeviceId:<DeviceGUID> /machinepool:<machine pool>
    ```

    Example:

    `KitsDeviceDetector.exe /Physical:Fake_PC.dll /DeviceName:mydevice /DeviceId:00000015-c0fb-79c3-0000-000000000000 /machinepool:$\mypool`
    
    -  If testing with a Health image, include the following parameter:
    `/imageprofile:health`

    -  If the image installed on the DUT is not a lab or a health image, include the following parameter:
    `/SkipFFUCheck`

    -  The KitsDeviceDetector log can found at %ProgramFiles(x86)%\\WTTMobile\\Tools\\KitsDeviceDetector.log

     

9.  Restart the proxy service in elevated mode.
    1.  In the Proxy Service command prompt window, press CTRL + C to stop the service.
    2.  Restart the Proxy Service double clicking on the "WTT Proxy" shortcut on the desktop of the Proxy System, or by navigating to %ProgramFiles(X86)%\\WTTMobile\\Client\\ and running the following command from the elevated command prompt:

        ```syntax
        WTTProxy.exe -console
        ```

10. Validation: After running device detector (steps above), the device should be booted to a valid OS, and be a visible target that shows as Ready in HLK Manager and HLK Studio.

## <span id="Onboarding_Aries_connected_devices"></span><span id="onboarding_aries_connected_devices"></span><span id="ONBOARDING_ARIES_CONNECTED_DEVICES"></span>Onboarding Aries connected devices


1.  On the Proxy system, launch an elevated command prompt.
2.  Navigate to %ProgramFiles(x86)%\\WTTMobile\\Tools\\
3.  To onboard the device, run the following command from the elevated command prompt:

    ``` syntax
    KitsDeviceDetector.exe /devicefilters:<aries name> /machinepool:<machine pool>
    ```

    Example:

    `KitsDeviceDetector.exe /devicefilters:myaries  /machinepool:$\mypool`

    - The image on the device must be either a lab image or a health image.

    -  If testing with a Health image, include the following parameter:
    `/imageprofile:health`

    -  To flash an image on your device as part of the onboarding process, include the following parameter
    `/ImagePath:<full path to the flash_lab.ffu image>`
    
    Example:
    
    `/ImagePath:C:\flash_lab.ffu`

    -  To find the name of the Aries dongles on the network, use %ProgramFiles(x86)%\\WTTMobile\\Tools\\AriesUtil.exe . The command **AriesUtil.exe Discover** will return the full list of available devices. A firewall exception must be added for AriesUtil.exe prior to use. If no devices are detected, you may need to use the **/Adapter** parameter. The adapter type can be determined by opening the Networking and Sharing Center on the controller, the Adapter is listed under **Connections**. The most common Adapter value is **Ethernet**. Use the command **AriesUtil.exe /?** for a complete list of available commands.

    -  The KitsDeviceDetector log can found at %ProgramFiles(x86)> %\\WTTMobile\\Tools\\KitsDeviceDetector.log

    For more information on HLK mobile testing tools and utilities, see [HLK Mobile Testing Tools and Utilities](../user/hlk-mobile-testing-tools-and-utilities.md)


4.  Restart the proxy service in elevated mode.
    1.  In the Proxy Service command prompt window, press CTRL + C to stop the service.
    2.  Restart the Proxy Service double clicking on the "WTT Proxy" shortcut on the desktop of the Proxy System, or by navigating to %ProgramFiles(X86)%\\WTTMobile\\Client\\ and running the following command from the elevated command prompt:

        ```syntax
        WTTProxy.exe -console
        ```

5.  \[For Health image only\] - After KitsDeviceDetector is complete, run the following commands from %ProgramFiles(x86)%\\WTTMobile\\Tools\\

    ```syntax
    AriesUtil.exe ResetDevice /Aries:<aries-name> [/Autoskip:true]
    ```

6.  Validation: After running device detector (steps above), the device should be booted to a valid OS, and be a visible target that shows as Ready in HLK Manager and HLK Studio.

## Onboarding Ethernet connected devices

1.  On the Proxy system, launch an elevated command prompt.
2.  Navigate to %ProgramFiles(x86)%\\WTTMobile\\Tools\\
3.  Get the connection string for your device:
    1.  Boot the device and find the IP address.
    2.  From the elevated command prompt, run the following command:

        ```syntax
        KitsDeviceDetector.exe /rundevicediscovery
        ```

        This command will output all of the devices on the subnet that has Sirep running. Each string will look something like this:
        > Name: 8CAE4CF5D6A5 | UniqueId: 00000000-0000-0000-0000-8cae4cf5d6a5 | Address: 10.131.2.211 | Connection: SirepBroadcast1 | Location:

         

4.  Find your device string (matching your IP address, and make note of the following fields:
    1.  "Name:"
    2.  "UniqueId:"
5.  To onboard the device, run the command from the elevated command prompt:

    ```syntax
    KitsDeviceDetector.exe /machinepool:$\Pool /Physical:Fake_PC.dll /DeviceName:NAME_OF_DEVICE /DeviceId:<DeviceGUID> /SkipFFUCheck
    ```

    Example:

    `KitsDeviceDetector.exe /machinepool:$\Test_Pool /Physical:Fake_PC.dll /DeviceName:8CAE4CF5D6A5 /DeviceId:00000000-0000-0000-0000-8CAE4CF5D6A5 /SkipFFUCheck`

6.  Restart the proxy service in elevated mode.
    1.  In the Proxy Service command prompt window, press CTRL + C to stop the service.
    2.  Restart the Proxy Service double clicking on the "WTT Proxy" shortcut on the desktop of the Proxy System, or by navigating to %ProgramFiles(X86)%\\WTTMobile\\Client\\ and running the following command from the elevated command prompt:

        ```syntax
        WTTProxy.exe -console
        ```

7.  Validation: After running device detector (steps above), the device should be booted to a valid OS, and be a visible target that shows as Ready in HLK Manager and HLK Studio.




