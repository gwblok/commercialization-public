---

Description: 'We''re now going to take an app (like the sample Hello, World! app), and package it up so that it can be serviced after it reaches your customers.'
ms.assetid: a801d768-0397-4f85-b68f-bd85ddcc3f1f
MSHAttr: 'PreferredLib:/library'
title: 'Lab 1b: Add an app to your image'

ms.date: 10/15/2018
ms.topic: article


---

# Lab 1b: Add an app to your image

We're now going to take an app (like the sample [IoT Core Default](https://github.com/ms-iot/samples/tree/develop/IoTCoreDefaultApp) app), package it up, and create a new image you can load onto new devices. 

For background apps, use the same method to install and run them. Note, only one app can be selected as the startup app, all other apps installed using this method run as background apps.

**Note**  As we go through this manufacturing guide, ProjectA will start to resemble the SampleA image that's in C:\\IoT-ADK-AddonKit\\Source-arm\\Products\\SampleA.

## <span id="Prerequisites"></span><span id="prerequisites"></span><span id="PREREQUISITES"></span>Prerequisites

We'll use the ProjectA image we created from [Lab 1a: Create a basic image](create-a-basic-image.md).

## Create an appx package

You can skip these steps if you've already created and tested your app.

1.  Create a UWP app. This can be any app designed for IoT Core, saved as an Appx Package. For our example, we use the [IoT Core Default](https://github.com/ms-iot/samples/tree/develop/IoTCoreDefaultApp) app.

2.  In Visual Studio, to save the IoT Core Default app as an Appx package, click **Project > Store > Create App Packages** > **No** > **Next**. 

3.  Select **Output location: C:\DefaultApp** (or any other path that doesn't include spaces.)
    
4.  Select **Generate app bundle: Never**
    
5.  Click **Create**.

    Visual Studio creates the Appx file into C:\DefaultApp\IoTCoreDefaultApp_1.2.0.0_ARM_Debug_Test 

6.  Optional: [Test the app](test-the-app.md). Note, you may have already tested the app as part of building the project. 


## <span id="Package_the_app"></span><span id="package_the_app"></span><span id="PACKAGE_THE_APP"></span>Package the app

**Create a package for an app**


1.  From the IoT Core Shell, create a new **appx package** using [New-IoTAppxPackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTAppxPackage.md)

    ``` powershell
    Add-IoTAppxPackage "C:\DefaultApp\IoTCoreDefaultApp_1.2.0.0_ARM_Debug_Test\IoTCoreDefaultApp_1.2.0.0_ARM_Debug_Test.appx" fga Appx.MyUWPApp

    (or) newappxpkg "C:\DefaultApp\IoTCoreDefaultApp_1.2.0.0_ARM_Debug_Test\IoTCoreDefaultApp_1.2.0.0_ARM_Debug_Test.appx" fga Appx.MyUWPApp
    ```

    This creates a new folder at `C:\MyWorkspace\Source-<arch>\Packages\Appx.MyUWPApp`, copies the appx files and its dependencies and generates a customizations.xml file as well as a package xml file that is used to build the package.

    This also adds a FeatureID **APPX_MYUWPAPP** to the `C:\MyWorkspace\Source-<arch>\Packages\OEMFM.xml` file.

3.  From the IoT Core Shell, build the package using [New-IoTCabPackage](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/New-IoTCabPackage.md).

    ``` powershell
    New-IoTCabPackage Appx.MyUWPApp
    (or) buildpkg Appx.MyUWPApp
    ```

    The package is built, appearing as `C:\MyWorkspace\Build\<arch>\pkgs\<oemname>.Appx.MyUWPApp.cab`.


## <span id="Update_the_project_s_configuration_files"></span><span id="update_the_project_s_configuration_files"></span><span id="UPDATE_THE_PROJECT_S_CONFIGURATION_FILES"></span>Update the project's configuration files

**Replace your product's default app with your own**

1.  Add the FeatureID for our app package using [Add-IoTProductFeature](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Add-IoTProductFeature.md)

    ``` powershell
    Add-IoTProductFeature ProductA Test APPX_MYUWPAPP -OEM
    (or) addfid ProductA Test APPX_MYUWPAPP -OEM
    ```

2. Remove the sample test apps IOT_BERTHA using [Remove-IoTProductFeature](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Remove-IoTProductFeature.md)

    ``` powershell
    Remove-IoTProductFeature ProductA Test IOT_BERTHA
    (or) removefid ProductA Test IOT_BERTHA
    ```

## <span id="Build_and_test_the_image"></span><span id="build_and_test_the_image"></span><span id="BUILD_AND_TEST_THE_IMAGE"></span>Build and test the image

Build and flash the image using the same procedures from [Lab 1a: Create a basic image](create-a-basic-image.md). Short version:

1.  From the IoT Core Shell, build the image (`buildimage ProductA Test`).
2.  Install the image: Start **Windows IoT Core Dashboard** > Click the **Setup a new device** tab >  select **Device Type: Custom** >
3.  From **Flash the pre-downloaded file (Flash.ffu) to the SD card**: click **Browse**, browse to your FFU file (`C:\MyWorkspace\Build\<arch>\ProductA\Test\Flash.ffu`), then click **Next**.
4.  Enter the device name and password. Put the Micro SD card in the device, select it, accept the license terms, and click **Install**. 
4.  Put the card into the IoT device and start it up.

After a short while, the device should start automatically, and you should see your app.

## <span id="Next_steps"></span><span id="next_steps"></span><span id="NEXT_STEPS"></span>Next steps

[Lab 1c: Add a file and a registry setting to an image](add-a-registry-setting-to-an-image.md)

## <span id="Related_topics"></span> Related topics

[Update apps on your IoT Core devices](https://docs.microsoft.com/windows-hardware/service/iot/updating-iot-core-apps)
