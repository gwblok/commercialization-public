---

Description: 'To get started, we''ll create a basic Windows 10 IoT Core (IoT Core) image, flash it to a micro SD card, and put it into a device to make sure that everything''s working properly.'
ms.assetid: aeba79b8-d8dd-481a-a8bf-03ae28174632
MSHAttr: 'PreferredLib:/library'
title: 'Lab 1a: Create a basic image'

ms.date: 10/15/2018
ms.topic: article


---

# Lab 1a: Create a basic image

To get started, we'll create a basic Windows 10 IoT Core (IoT Core) image, flash it to a micro SD card, and put it into a device to make sure that everything's working properly. 

We'll create a product folder that represents our first design. For our first product design, we'll customize just enough for the IoT core device to boot up and run the built-in OOBE app, which we should be able to see on an HDMI-compatible monitor.

To make running these commands easier, we'll install and use the IoT Core shell, which presets several frequently-used paths and variables.

## Prerequisites

See [Get the tools needed to customize Windows IoT Core](set-up-your-pc-to-customize-iot-core.md) to get your technician PC ready. 

## Create a basic image

### Create a workspace

1.  In Windows Explorer, go to the folder where you installed the IoT Core ADK Add-Ons, for example, **C:\\IoT-ADK-AddonKit**, and open **IoTCorePShell.cmd**. It should prompt you to run as an administrator.
    
    This will load the powershell module and also check the versions of the ADK, IoT Core kit. This will also check for the test certificates in the certificate store and if not present, install them automatically.
	
	Troubleshooting: Error: "The system cannot find the path specified". If you get this, right-click the icon and modify the path in "Target" to the location you've chosen to install the tools.

2.  In the IoTCorePShell, create a new workspace say `C:\MyWorkspace` with an OEM name `Contoso` for the architecture `arm` using [New-IoTWorkspace](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/New-IoTWorkspace.md)
    ``` powershell
    New-IoTWorkspace C:\MyWorkspace Contoso arm
    (or) new-ws C:\MyWorkspace Contoso arm
    ```
    
    IoT Core supports four architectures, x64,x86,arm and arm64. 
    
    Only alphanumeric characters are supported in the OEM name as this is used as a prefix for various generated file names.
    
    This generates the IoTWorkspace.xml and sets a version number for the design, which you can use for future updates. The first version number defaults to 10.0.0.0.
    (Why a four-part version number? Learn about versioning schemes in [Update requirements](https://docs.microsoft.com/windows-hardware/service/mobile/update-requirements)).

    The required packages such as Registry.Version, Custom.Cmd and Provisioning.Auto will be imported into the workspace automatically.

    ![IoTCorePShell](images/IotCorePShell1.png)

3. Import sample packages into the workspace. You may choose to import the packages selectively or import all.
    ``` powershell
    # Importing Recovery packages from sample workspace
    Import-IoTOEMPackage Recovery.*
    (or) importpkg Recovery.*
    # Below example imports all packages from the sample workspace
    Import-IoTOEMPackage *
    (or) importpkg *
    ```


### Import a Raspberry Pi BSP 

1. Download [RPi_BSP.zip](https://github.com/ms-iot/iot-adk-addonkit/releases/download/17134_v5.3/RPi_BSP.zip) to a local directory, say `C:\Downloads\RPi_BSP.zip`.

2. Import the bsp using [Import-IoTBSP](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-IoTBSP.md)
    ``` powershell
    Import-IoTBSP RPi2 C:\Downloads\RPi_BSP.zip
    (or) importbsp RPi2 C:\Downloads\RPi_BSP.zip
    ```
    For more information on available BSPs, see [Windows 10 IoT Core BSPs](https://docs.microsoft.com/windows/iot-core/build-your-image/createbsps).

### Build packages

1. From the IoT Core Shell, get your environment ready to create products by building all of the packages in the working folders. Build packages using [New-IoTCabPackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/New-IoTCabPackage.md)

    ``` powershell
    New-IoTCabPackage All
    (or) buildpkg All
    ```

### <span id="Create_a_test_project"></span>Create a test project

1. From the IoT Core Shell, create a new product folder that uses the Rpi2 BSP. This folder represents a new device we want to build, and contains sample customization files that we can use to start our project. Create a new product using [Add-IoTProduct](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTProduct.md)

    ``` powershell
    Add-IoTProduct ProductA RPi2
    (or) newproduct ProductA RPi2
    ```
    You will be prompted to enter the **SMBIOS** information such as Manufacturer name (oem name), Family, SKU, BaseboardManufacturer and BaseboardProduct.

    The BSP name is the same as the folder name for the BSP. You can see which BSPs are available by looking in the `C:\MyWorkspace\Source-<arch>\BSP` folders.

    This creates the folder: `C:\MyWorkspace\Source-<arch>\Products\\ProductA`.

    ![New Product](images/IotCorePShell2.png)

### <span id="Build_an_image"></span>Build an image

1.  Eject any removable storage drives, including the Micro SD card and any USB flash drives.

2.  From the IoT Core Shell, build a flashable test image using the default files. Test images include additional tools, and you can create test images using either signed or unsigned test packages. Build the image using [New-IoTFFUImage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/New-IoTFFUImage.md)

    ``` powershell
    New-IoTFFUImage ProductA Test
    (or) buildimage ProductA Test
    ```

    This builds an FFU file with your basic image at `C:\MyWorkspace\Build\<arch>\ProductA\Test`.

    Troubleshooting:
	
	-  ERROR CODES: 0x80070005 or 0x800705b4: Unplug all external drives (including micro SD cards and USB thumb drives), and try again.  
	If this doesn't work, go back to [Set up your PC and download the samples](set-up-your-pc-to-customize-iot-core.md) and make sure everything's installed.

### <span id="Flash_an_image"></span>Flash the image to a memory card

1.  Start the **Windows IoT Core Dashboard**.

2.  Plug your micro SD card into your technician PC, and select it in the tool.

3.  From **Setup a new device**, select Device Type: **Custom**.

4.  From **Flash the pre-downloaded file (Flash.ffu) to the SD card**, click **Browse**, browse to your FFU file (`C:\MyWorkspace\Build\<arch>\ProductA\Test\Flash.ffu`), then click **Next**.

5.  Optional: Change the default device name (Default is minwinpc.) 

6.  Enter your device password.

7.  Accept the license terms, and then click **Install**. The Windows IoT Core Dashboard formats the micro SD card and installs the new image.

### <span id="Try_it_out"></span>Try it out

1.  Connect your IoT device, such as a Raspberry Pi 3, into a monitor using an HDMI cable.
    **Note**  When possible, use a direct connection to an HDMI port. The display may not appear when using DVI/VGA adapters or hubs.

2.  Put in the micro SD card with your image.

3.  Power it on.

    After a short while, the device should start automatically, and you should see the [IoT Core Default app](https://docs.microsoft.com/en-us/windows/iot-core/develop-your-app/iotcoredefaultapp) (code-named "Bertha"), which shows basic info about the image.

    **Note**  Some devices may be extremely slow to boot up on the first boot when using some 8GB class 10 SD cards. Slow boot times may be over 15 minutes. Subsequent boots will be much quicker on the affected cards.

See also [Set up your device](https://developer.microsoft.com/windows/iot/getstarted/prototype/setupdevice) for more instructions on flashing the device.

## <span id="Next_steps"></span><span id="next_steps"></span><span id="NEXT_STEPS"></span>Next steps

Leave the device on for now, and continue to [Lab 1b: Add an app to your image](deploy-your-app-with-a-standard-board.md).
