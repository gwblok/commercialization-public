---

Description: Preinstall Apps Using DISM
ms.assetid: 707607d6-eb3a-4a5b-b52d-4d465d82f69d
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Preinstall Apps Using DISM

ms.date: 04/25/2018
ms.topic: article
---

# Preinstall Apps Using DISM


> [!Note]
> Interested in preinstalling Microsoft Store apps, but you aren’t an OEM? For information about sideloading apps for organizations, see [Sideload Apps with DISM](sideload-apps-with-dism-s14.md).

This topic covers how to preinstall apps so they are included as part of a Windows image.

> [!tip]
> Hardware Support Apps (HSAs) are Microsoft Store Apps, and the following instructions apply.

## <span id="BKMK_WorkWithAppPackages"></span><span id="bkmk_workwithapppackages"></span><span id="BKMK_WORKWITHAPPPACKAGES"></span>Work with app packages


Use DISM to offline provisioning an app into an image. You can use DISM from the Command Prompt, or the DISM cmdlets in Windows PowerShell.

In previous versions of Windows 10, preinstalled Universal apps and Microsoft Store apps had to be pinned to the Start menu. Windows would remove apps that were preinstalled but not pinned to the Start menu.

Starting with Windows 10, version 1803, apps can be preinstalled without being pinned to the Start Menu when you use `DISM /add-provisionedappxpackage` with the `/region` option. When you preinstall an app, you can choose to leave the app out of your LayoutModification.xml and the app will successfully install without appearing as a Start Menu tile. When a list of regions is NOT specified, the app will be provisioned only if it is pinned to start layout. 


### Extract the package files

1.  Browse to the folder where you saved the app packages that you downloaded from the Partner Dashboard.
2.  Right-click each .zip folder containing your app package files. Click **Extract All** and select a location to save the package file folders.

    The folder contains the all of the unpacked files for the package, including a main package, any dependency packages, and the license file.

> [!important]
> Don't modify the folder once you have extracted the package files. If you change, add, or remove any files in the folder, the app will fail either during installation or launch. Even browsing the folder may cause problems.

You’ll need to use the license file from the package files to test your provisioned image. Creating your own custom data file will not allow you to accurately test an app preinstalled by an OEM.

For offline provisioning of an app into an image, you can use either the Dism.exe tool or the DISM cmdlets in Windows PowerShell to add an app from a folder of unpacked files.

### Preinstall a Microsoft Store-signed app with DISM

1.  Open the Command Prompt as administrator. 

2.  Mount a Windows image for that you want to service:

    ```
    Dism /Mount-Image /ImageFile:c:\images\myimage.wim /Index:1 /mountdir:c:\test\offline
    ```

3.  Add the app to the mounted image. Use the `/PackagePath` and `/DependencyPackagePath` options. 
    - `Packagepath` is the path to the .appx bundle or package file
    - `DependencyPackagePath` is the path for specifying each dependency package. You can have more than one dependency per command.
    - **New in Windows 10, version 1803**: Use the `Region` option when adding apps. `Region` allows you to add an app without having to pin the app to the Start Menu.

    ```
    Dism /Image:c:\test\offline /Add-ProvisionedAppxPackage /PackagePath:c:\downloads\package.appxbundle /DependencyPackagePath:c:\downloads\dependency1.appx /DependencyPackagePath:c:\downloads\dependency2.appx /LicensePath=c:\downloads\package_License1.xml /region=all"
    ```

    See [DISM app package servicing command-line options](dism-app-package--appx-or-appxbundle--servicing-command-line-options.md) for information about working with app packages, including the new /region option..

4.  Pin the app to the Start Menu.

    - If you didn't specify `/region` when preinstalling the app, pin the app to the Start Menu with [LayoutModification.xml](https://docs.microsoft.com/en-us/windows/configuration/start-layout-xml-desktop). 

      **or**

    - If you did specify `/region` when preinstalling the app, and you want to pin the app to the Start Menu for specific regions, use the [`RequiredStartGroups Region="region1|region2"` element in LayoutModification.xml](https://docs.microsoft.com/en-us/windows/configuration/start-layout-xml-desktop#requiredstartgroups) to specify the regions where you want the app to appear.

5.  Save changes and unmount the image. At the command prompt, type:

    ```
    Dism /Unmount-Image /mountdir:c:\test\offline /commit
    ```


> [!note]
> Microsoft Store apps don't run in audit mode. To test your deployment, run Windows and create a new user profile. For more information about audit mode, see [Audit mode overview](audit-mode-overview.md).

 

**Important**   If you are preinstalling a mobile broadband device app, you must insert the SIM card in the PC before you run the specialize phase of Sysprep. For more information about preinstalling a mobile broadband device app, see [Preinstall the Necessary Components for a Mobile Broadband Application Experience](#bkmk_broadband_intro).



## <span id="BKMK_UpdateOrRemovePackages"></span><span id="bkmk_updateorremovepackages"></span><span id="BKMK_UPDATEORREMOVEPACKAGES"></span>Update or remove packages


You can remove a preinstalled app, including the license and custom data files, from a Windows image by using the DISM.exe tool or the DISM cmdlets in Windows PowerShell. You should remove the old version of the app before installing a new one.

### Remove a preinstalled app by using DISM

1.  Open the Deployment Tools Command Prompt, installed with the Windows ADK, with administrator privileges. From the Start screen, type **Deployment and Imaging Tools Environment**, right-click the icon, and select **Run as Administrator**.
2.  Mount the offline image for servicing. At the command prompt, type:

    ```
    Dism /Mount-Image /ImageFile:c:\images\myimage.wim /Index:1 /mountdir:c:\test\offline
    ```

3.  Find the full package name of the app that you want to remove. At the command prompt, type:

    ```
    Dism /Image:C:\test\offline /Get-ProvisionedAppxPackages
    ```

4.  Remove the app from the mounted image. For example, at the command prompt, type:

    ```
    Dism /Image:c:\test\offline /Remove-ProvisionedAppxPackage /PackageName:microsoft.devx.appx.app1_1.0.0.0_neutral_en-us_ac4zc6fex2zjp
    ```

   
5.  If you want to update the app, you can preinstall the updated version of the Microsoft Store-signed app. At a command prompt, type:

    ```
    Dism /Image:c:\test\offline /Add-ProvisionedAppxPackage/FolderPath:c:\downloads\appxpackage
    ```

6.  Save changes and unmount the image. At the command prompt, type:

    ```
    Dism /Unmount-Image /mountdir:c:\test\offline /commit
    ```


## <span id="BKMK_UseCustomDateFiles"></span><span id="bkmk_usecustomdatefiles"></span><span id="BKMK_USECUSTOMDATEFILES"></span>Use custom data files


Apps that are preinstalled on a PC can access custom data specific to the installation. This custom data is added to the app during preinstallation and becomes available at runtime. Custom data enables developers to customize an app's features and functionality, including providing reporting capabilities.

### <span id="BKMK_AddCustomDataFile"></span><span id="bkmk_addcustomdatafile"></span><span id="BKMK_ADDCUSTOMDATAFILE"></span>Add a custom data file to a Windows image

You must specify the custom data file when you preinstall the app by using the DISM tool and through Windows PowerShell using the **Add-AppxProvisionedPackage** cmdlet. The following command shows how to do this using the DISM tool:

```
Dism /Image:C:\test\offline /Add-ProvisionedAppxPackage / FolderPath:f:\Apps\Fabrikam_KnowMyPC /CustomDataPath:f:\Contoso_Promotion.xml
```

If a custom data file already exists in the data store for an app—for example, if the package has already been added to the image—the existing file is overwritten. If the installation fails, the file isn't restored.

**Note**  
You can release updates to an app through the Microsoft Store without losing the custom data file. However, if a user deletes the app, the custom data file is no longer available, even if the user reinstalls the app.

 

### <span id="BKMK_TestCustomDataFile"></span><span id="bkmk_testcustomdatafile"></span><span id="BKMK_TESTCUSTOMDATAFILE"></span>Test custom data for preinstalled apps

Apps that are preinstalled on a PC can access custom data specific to the installation. This custom data is added to the app during preinstallation and becomes available to the app at runtime. Custom data enables developers to customize an app's features and functionality, including providing reporting capabilities.

The Custom.data file appears at the app's installed location. The name Custom.data is hard-coded and can't be modified. Your app can check for the existence of this file to determine if the app was preinstalled on the PC. Here's an example of how to access the Custom.data file.

```
var outputDiv = document.getElementById("CustomData");
Windows.ApplicationModel.Package.current.installedLocation.getFileAsync
     ("microsoft.system.package.metadata\\Custom.data").then(function (file) {
         // Read the file
         Windows.Storage.FileIO.readTextAsync(file).done(function (fileContent) {
            outputDiv.innerHTML = 
                 "App is preinstalled. CustomData contains:<br /><br />"
                 + fileContent;
         },
         function (error) {
             outputDiv.innerText = "Error reading CustomData " + error;
         });
     },
     function (error) {
         outputDiv.innerText = "CustomData was not available. App not preinstalled";
     });
```

Your Custom.data file can include any content and be in any format your app requires. The preinstallation process simply makes it available to your app. Developers can supply the data file to the preinstallation partner, or you can agree to a format that enables the partner to generate the content.

### <span id="Test_your_custom_data"></span><span id="test_your_custom_data"></span><span id="TEST_YOUR_CUSTOM_DATA"></span>Test your custom data

When you're building and debugging your app in Microsoft Visual Studio, you can't access the Custom.data file from the app's installed location because the app isn't preinstalled yet. You can simulate using your Custom.data file by putting a test Custom.data file in the app itself, and then loading and testing the app local file. To do this, modify the code sample from:

```
("microsoft.system.package.metadata\\Custom.data").then(function (file) {
```

to:

```
("Custom.data").then(function (file) {
```

After you have verified your file format and content, you can change the location of the Custom.data file to the final location, as shown in the original example above.

**To test your Custom.data file**

1.  Open the Deployment Tools Command Prompt, installed with the Windows ADK, with administrator privileges. From the Start screen, type **Deployment and Imaging Tools Environment**, right-click the icon, and select **Run as Administrator**.
2.  Add the application with the custom data file:

    ```
    dism /online /Add-ProvisionedAppxPackage /PackagePath:.\CustomData_1.0.0.1_AnyCPU_Debug.appx /CustomDataPath:.\Test.txt /SkipLicense
    ```

    Where `/PackagePath:.\CustomData_1.0.0.1_AnyCPU_Debug.appx` points to your local app test package, and where `/CustomDataPath:.\Test.txt` points to your Custom.data file. Be aware that the file name you provide here isn't used after the data is installed in your app.

    The app now has a tile on the **Start** screen of the PC used to test the app. The app should be able to access the Custom.data file. If additional debugging is needed, attach a debugger after starting the app from the **Start** screen.

    **Note**   You might be required to sign out and sign in again to see the app on the **Start** screen.

     

3.  After you're done testing your app, you must remove the preinstalled package to continue using your Dev environment. To remove the preinstalled package using Windows PowerShell, you can use the **Get-AppxPackage** cmdlet to provide the full app package name through the pipeline to the **Remove-ProvisionedAppxPackage** cmdlet:

    `Get-AppxPackage *CustomData* | Remove-ProvisionedAppxPackage`

    Where `*CustomData*` is the known part of your app's name

## <span id="BKMK_broadband_intro"></span><span id="bkmk_broadband_intro"></span><span id="BKMK_BROADBAND_INTRO"></span>Preinstall a Microsoft Store device app or mobile broadband app


You can preinstall the necessary components for a Microsoft Store device app or a mobile broadband app using the Deployment Image Servicing and Management (DISM) platform.

**Note**   This article is intended for OEMs, who will be supporting a Microsoft Store device app or the mobile broadband app on their devices.

 

For each type of app, two things should be preinstalled to provide the correct Microsoft Store device app or mobile broadband app:

-   Microsoft Store device app, preinstall:
    1.  The device metadata package
    2.  The app
-   Microsoft Store mobile broadband app, preinstall:
    1.  The service metadata package
    2.  The app

**Important**   Although metadata packages and the corresponding apps are parsed immediately after the OOBE process completes, a user might be able to launch the app before the metadata package is parsed. In this case, the user will see an access denied error. To avoid this, apply both the metadata package and the app to the system image.

 

## <span id="Preinstall_the_device_metadata_or_service_metadata_package"></span><span id="preinstall_the_device_metadata_or_service_metadata_package"></span><span id="PREINSTALL_THE_DEVICE_METADATA_OR_SERVICE_METADATA_PACKAGE"></span>Preinstall the device metadata or service metadata package


**To preinstall a device metadata or service metadata package**

1.  If you are preinstalling a Microsoft Store device app then you should have acquired the device metadata package. If you are preinstalling a mobile broadband app then you should have acquired the service metadata package.

    **Note**   Device metadata packages and service metadata packages use the same file name extension (.devicemetadata-ms).

     

2.  Copy the device metadata or service metadata package (devicemetadata-ms file) to your system image in the **%ProgramData%\\Microsoft\\Windows\\DeviceMetadataStore** folder. You can do this in one of the following ways:

    -   Online before running Sysprep
    -   Offline after running Sysprep by using DISM. To do this:

        1.  Mount the offline image for servicing.

            ```
            Dism /Mount-Image /ImageFile:C:\test\images\myimage.wim /index:1 /MountDir:C:\test\offline
            ```

        2.  Copy the metadata package files to the device metadata store of the mounted image. For example, to copy the **0ECF2029-2C6A-41AE-9E0A-63FFC9EAD877.devicemetadata-ms** metadata package file to the device metadata store, **ProgramData\\Microsoft\\Windows\\DeviceMetadataStore**:

            ```
            copy 0ECF2029-2C6A-41AE-9E0A-63FFC9EAD877.devicemetadata-ms C:\test\offline\ProgramData\Microsoft\Windows\DeviceMetadataStore
            ```

        3.  Save the changes and unmount the image.

            ```
            dism /Unmount-Image /mountdir: c:\test\offline /commit
            ```

        For more info about offline image servicing, see [DISM Overview](http://technet.microsoft.com/library/hh825236.aspx).

For more info about service metadata, see [Service metadata](http://go.microsoft.com/fwlink/p/?LinkId=698640).

## <span id="Preinstall_the_Windows_Store_device_app_or_mobile_broadband_app"></span><span id="preinstall_the_windows_store_device_app_or_mobile_broadband_app"></span><span id="PREINSTALL_THE_WINDOWS_STORE_DEVICE_APP_OR_MOBILE_BROADBAND_APP"></span>Preinstall the Microsoft Store device app or mobile broadband app


**To preinstall the Microsoft Store device app or mobile broadband app**

1.  Mount the offline image for servicing.

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\myimage.wim /index:1 /MountDir:C:\test\offline
    ```

2.  Add the Microsoft Store device app or mobile broadband app to the image.

    ```
    dism /Image:<mounted folder> /Add-ProvisionedAppxPackage /FolderPath:<appxpackage path>
    ```

3.  Save the changes and unmount the image.

    ```
    dism /Unmount-Image /mountdir: c:\test\offline /commit
    ```