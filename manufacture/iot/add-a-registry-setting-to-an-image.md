---

Description: 'We''ll create some test files and registry keys to the image, again packaging them up so that they can be serviced after they reach your customers.'
ms.assetid: 7ca2b835-4d36-43d9-b46f-d5d5d8410335
MSHAttr: 'PreferredLib:/library'
title: 'Lab 1c: Add a file and a registry setting to an image'

ms.date: 10/15/2018
ms.topic: article


---

# Lab 1c: Add a file and a registry setting to an image

Files and registry keys that you add to your image often won't be specific to an architecture. For these, we recommend creating a common package that you can use across all of your device architectures.
 
We'll create some test files and registry keys to the image, and again package them up so that they can be serviced after they reach your customers.

We'll add these to the common feature manifest (OEMCommonFM.xml), which is used in x86, x64, and ARM builds.

For this lab, we'll start an new product, ProductB, so that later we can use the IoT sample app to get the IP address of our device and verify that our files and reg keys have made it. 

## <span id="Prerequisites"></span><span id="prerequisites"></span><span id="PREREQUISITES"></span>Prerequisites

See [Get the tools needed to customize Windows IoT Core](set-up-your-pc-to-customize-iot-core.md) to get your technician PC ready.

## <span id="Create_your_test_files"></span><span id="create_your_test_files"></span><span id="CREATE_YOUR_TEST_FILES"></span>Create your test files

-   Create a few sample text files using Notepad, add some random text so that the files are not empty, title them TestFile1.txt and TestFile2.txt.

## <span id="Build_a_package_for_your_test_files"></span><span id="build_a_package_for_your_test_files"></span><span id="BUILD_A_PACKAGE_FOR_YOUR_TEST_FILES"></span>Build a package for your test files

1.  Open the IoT Core Shell: run `C:\MyWorkspace\IoTCorePShell.cmd` as an administrator.

2.  Create a **File package** using [Add-IoTFilePackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTFilePackage.md)

    ``` powershell
    # Array of files with destinationDir, Source and destinationFilename
    $myfiles = @(
        ("`$(runtime.system32)","C:\Temp\TestFile1.txt", ""),        
        ("`$(runtime.bootDrive)\OEMInstall","C:\Temp\TestFile2.txt", "TestFile2.txt")
        )
    Add-IoTFilePackage Files.Configs $myfiles
    ```

    This creates a new folder at `C:\MyWorkspace\Common\Packages\Files.Configs`.

    This also adds a FeatureID **FILES_CONFIGS** to the `C:\MyWorkspace\Common\Packages\OEMCOMMONFM.xml` file.

    Variables like `$(runtime.system32)` are defined in `C:\Program Files (x86)\Windows Kits\10\Tools\bin\i386\pkggen.cfg.xml`.

3. Create a **Registry package** using [Add-IoTRegistryPackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTRegistryPackage.md)
    ``` powershell
    # Array of files with destinationDir, Source and destinationFilename
    $myregkeys = @(
        ("`$(hklm.software)\`$(OEMNAME)\Test","StringValue", "REG_SZ", "Test string"),
        ("`$(hklm.software)\`$(OEMNAME)\Test","DWordValue", "REG_DWORD", "0x12AB34CD")
        )
    Add-IoTRegistryPackage Registry.Settings $myregkeys
    ```

    This creates a new folder at `C:\MyWorkspace\Common\Packages\Registry.Settings`.

    This also adds a FeatureID **REGISTRY_SETTINGS** to the `C:\MyWorkspace\Common\Packages\OEMCOMMONFM.xml` file.

4.  Build the packages using [New-IoTCabPackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/New-IoTCabPackage.md). (The `buildpkg All` command builds everything in the source folders.)

    ``` powershell
    New-IoTCabPackage Files.Configs
    (or) buildpkg Files.Configs
    New-IoTCabPackage Registry.Settings
    (or) buildpkg Registry.Settings
    ```

    The package is built, available at  `C:\MyWorkspace\Build\<arch>\pkgs`.

## <span id="Create_a_new_product"></span><span id="create_a_basic_image"></span><span id="CREATE_A_BASIC_IMAGE"></span>Create a new product

1.  Create a new product folder. 

    ``` powershell
    Add-IoTProduct ProductB RPi2
    (or) newproduct ProductB RPi2
    ```
    This will prompt you to enter **SMBIOS** values.

## <span id="Update_the_project_s_configuration_files"></span><span id="update_the_project_s_configuration_files"></span><span id="UPDATE_THE_PROJECT_S_CONFIGURATION_FILES"></span>Update the project's configuration files

1.  Update the product test configuration to include the features using [Add-IoTProductFeature](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTProductFeature.md)

    ``` powershell
    Add-IoTProductFeature ProductB Test FILES_CONFIGS -OEM
    (or) addfid ProductB Test FILES_CONFIGS -OEM
    Add-IoTProductFeature ProductB Test REGISTRY_SETTINGS -OEM
    (or) addfid ProductB Test REGISTRY_SETTINGS -OEM
    ```

## <span id="Build_and_test_the_image"></span><span id="build_and_test_the_image"></span><span id="BUILD_AND_TEST_THE_IMAGE"></span>Build and test the image

Build and flash the image using the same procedures from [Lab 1a: Create a basic image](create-a-basic-image.md). Short version:

1.  From the IoT Core Shell, build the image (`buildimage ProductB Test`).
2.  Install the image: Start **Windows IoT Core Dashboard** > Click the **Setup a new device** tab >  select **Device Type: Custom** >
3.  From **Flash the pre-downloaded file (Flash.ffu) to the SD card**: click **Browse**, browse to your FFU file (`C:\MyWorkspace\Build\<arch>\ProductB\Test\Flash.ffu`), then click **Next**.
4.  Enter device name and password.Put the Micro SD card in the device, select it, accept the license terms, and click **Install**. 
5.  Put the card into the IoT device and start it up.

After a short while, you should see the [IoT test (Bertha) app](https://developer.microsoft.com/windows/iot/samples/iotdefaultapp) which shows basic info about the image.

## <span id="See_your_files"></span>See if your files made it

1.  Connect both your technician PC and the device to the same ethernet network. 

    For example, to connect over a wired network, plug in a ethernet cable. To connect directly to the device, plug a network cable directly from your technician PC to the device.   

2.  On the test app, note the IP address, for example, 10.100.0.100. 

3.  On your technician PC, open File Explorer, and type in the IP address of the device with a \\\\ prefix and \\c$ suffix:

    ```
    \\10.100.0.100\c$
    ```

	Use the devicename, the default Administrator account, and password to log on. (Default is: minwinpc\\Administrator / p@ssw0rd)

4.  Check to see if the files exist. Look for:

    \\\\10.100.0.100\c$\\Windows\\system32\\TestFile1.txt

    \\\\10.100.0.100\c$\\OEMInstall\\TestFile2.txt

## <span id="See_your_regkeys"></span>See if your registry keys exist

1.  On your technician PC, connect to your device using an SSH client, such as [PuTTY](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe). For example, use the IP address and port 22 to connect to the device, then log in using the Administrator account and password. (To learn more, see [SSH](https://docs.microsoft.com/windows/iot-core/connect-your-device/SSH).)

2.  From the command line in the SSH client, query the system for the registry key.

    ```
    reg query HKLM\Software\Fabrikam\Test
    ```

    Where Fabrikam is your OEM name. The registry tool should return your test values.

## <span id="Next_steps"></span><span id="next_steps"></span><span id="NEXT_STEPS"></span>Next steps

[Lab 1d: Add a provisioning package to an image](add-a-provisioning-package-to-an-image.md)
