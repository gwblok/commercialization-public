---
title: Preload an app with a dependency
description: If you need to preinstall an app that has dependencies on other packages or components, you need to make sure that the other packages or components are preinstalled first before your app.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 74B736AD-E837-4F9F-8E34-F062688BCCC4


ms.date: 05/02/2017
ms.topic: article


---

# Preload an app with a dependency


OEMs can preload apps as long as they meet the requirements specified in the Windows 10 Mobile OEM Policy Document (OPD). For more information on how to create preloaded apps for mobile devices, see [Preinstallable apps for mobile devices](https://docs.microsoft.com/en-us/windows-hardware/customize/preinstall/preinstallable-apps-for-window-10-for-phones).

If you need to preinstall an app that has dependencies on other packages or components, you need to make sure that the other packages or components are preinstalled first before your app. If the dependent packages or components are not installed first, your app preinstall will fail.

<a href="" id="instructions"></a>**Instructions**  
**Prerequisites:**

1.  Make sure you have all the files you need to preload the OEM app:

    -   App source, such as an .appx or .appxbundle

    -   License file - This should be included as part of the preinstallation package.

    -   ProvXML file - See the section [Create a .provxml file for a preinstallable app](https://docs.microsoft.com/en-us/windows-hardware/customize/preinstall/preinstallable-apps-for-window-10-for-phones#create-a-provxml-file-for-a-preinstallable-app) for information on how to do this. When specifying the value of the **ProductID** parameter, this value must match the GUID from the AppxManifest file in the preinstallation package.

2.  Make sure you have the following files for the required component:

    -   App source, such as .appx or .appxbundle

    -   ProvXML file - This is a separate provisioning file from the one that corresponds to the primary app. When writing the provXML file, the value of the **ProductID** parameter must match the GUID from the AppxManifest file that corresponds to the required component.

    **Note**  Unlike the primary app, you do not need the license file for the required component when preloading it on the mobile device.

     

3.  Name your provXML files so that they meet the requirements outlined in this step.

    To make sure the required component is installed first, name the provXML files associated with the component in such a way that the file names precede the provXML file name for the primary app you want to preinstall. The OS preinstall logic uses the provXML file names to determine the order that apps and components are preinstalled so naming your required component so it alphabetically precedes the primary preinstall app ensures the dependency is resolved.

    For example, if you have a primary app called ContosoPartnerApp that's dependent on a framework called ContosoFramework, you can ensure the framework is installed first by using these naming suggestions:

    -   For the ContosoFramework provXML file, use a name that is similar to MPAP\_000ContosoFramework\_001.provxml.
    -   For the ContosoPartnerApp provXML file, use a name that is similar to MPAP\_aaaContosoPartnerApp\_001.provxml.

    In the Windows file system, "000" takes precedence over "aaa" so naming your provXML files this way ensures that the Contoso\_FrameworkApp is installed before Contoso\_PartnerApp.

**To preload the apps, build, and flash the OS image:**

1.  Create an package that contains the source file, license file, and provisioning file for the primary app.

    1.  Write a .pkg.xml and specify the source file, license file, and the .provXML file that corresponds to the primary app.

        The following code example shows how to do this.

        ```XML
        <?xml version="1.0" encoding="utf-8"?>
        <Package xmlns="urn:Microsoft.WindowsPhone/PackageSchema.v8.00"
           Owner=""
           OwnerType="OEM"
           ReleaseType="Production"
           Platform="PlatformName"
           Component="Phone"
           SubComponent="ContosoPartnerApp">
          <Components>
            <OSComponent>
              <Files>
                <File
                  Source="C:\Contoso\Customizations\Assets\ContosoPartnerApp.appxbundle"
                  DestinationDir="$(runtime.commonfiles)\Xaps" />
                <File
                  Source="C:\Contoso\Customizations\Assets\MPAP_aaaContosoPartnerApp_001.provxml" 
                  DestinationDir="$(runtime.commonfiles)\Provisioning\OEM" />   
                <File 
                  Source="C:\Contoso\Customizations\Assets\ContosoPartnerApp_License.xml"
                  DestinationDir="$(runtime.commonfiles)\Xaps" />  
              </Files>
            </OSComponent>
          </Components>
        </Package>
        ```

    2.  Specify the values for the **Owner**, **ReleaseType**, **Platform**, **Component**, and **SubComponent** elements.

    3.  Replace *C:\\Contoso\\Customizations\\Assets\\ContosoPartnerApp.appxbundle* with the location and file name of your app's source file.

    4.  Replace *C:\\Contoso\\Customizations\\Assets\\MPAP\_aaaContosoPartnerApp\_001.provxml* with the location and file name of your app's provisioning file.

    5.  Replace *C:\\Contoso\\Customizations\\Assets\\ContosoPartnerApp\_License.xml* with the location and file name of your app's license file.

    6.  Save the .pkg.xml file.

    7.  Run PkgGen to generate the .spkg from the .pkg.xml. 

2.  Create an package that contains the source file for the required component and the provisioning file that corresponds to it.

    1.  Write a .pkg.xml and specify the source file and the .provXML file that corresponds to the required package or component.

        The following code example shows how to do this.

        ```XML
        <?xml version="1.0" encoding="utf-8"?>
        <Package xmlns="urn:Microsoft.WindowsPhone/PackageSchema.v8.00"
           Owner=""
           OwnerType="OEM"
           ReleaseType="Production"
           Platform="PlatformName"
           Component="Phone"
           SubComponent="ContosoFramework">
          <Components>
            <OSComponent>
              <Files>
                <File
                  Source="C:\Contoso\Customizations\Assets\contoso-framework-app.appx"
                  DestinationDir="$(runtime.commonfiles)\Xaps" />
                <File
                  Source="C:\Contoso\Customizations\Assets\MPAP_000ContosoFramework_001.provxml" 
                  DestinationDir="$(runtime.commonfiles)\Provisioning\OEM" />   
              </Files>
            </OSComponent>
          </Components>
        </Package>
        ```

    2.  Specify the values for the **Owner**, **ReleaseType**, **Platform**, **Component**, and **SubComponent** elements.

    3.  Replace *C:\\Contoso\\Customizations\\Assets\\contoso-framework-app.appx* with the location and file name of the component's source file.

    4.  Replace *C:\\Contoso\\Customizations\\Assets\\MPAP\_000ContosoFramework\_001.provxml* with the location and file name of the package or component's provisioning file.

    5.  Save the .pkg.xml file.

    6.  Run PkgGen to generate the .spkg from the .pkg.xml. 

3.  Write down the location and names of the .spkg files that were generated for your primary app and the required component.

4.  Update your feature manifest file to include these new packages and define a feature name for them. For more information, see [Feature manifest file contents](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/feature-manifest-file-contents).

    1.  Edit the feature manifest file.

    2.  In the feature manifest file, locate the **OEM** group under **Features**.

    3.  Within the **OEM** group, define a feature name for the package containing the required component and the package containing the primary app.

        The following code example shows how to do this.

        ```XML
          <PackageFile Path="C:\Contoso\Customizations\Assets" Name="Owner.Component.SubComponent.ContosoFramework.spkg" > 
            <FeatureIDs> 
              <FeatureID>CONTOSO_FRAMEWORK</FeatureID> 
            </FeatureIDs> 
          </PackageFile> 

          <PackageFile Path="C:\Contoso\Customizations\Assets" Name="Owner.Component.SubComponent.ContosoPartnerApp.spkg" > 
            <FeatureIDs> 
              <FeatureID>CONTOSO_PARTNERAPP</FeatureID> 
            </FeatureIDs> 
          </PackageFile>
        ```

    4.  For each **PackageFile** element, change the values of the **Path** and **Name** attributes to match the location and name of your framework and app .spkg files.

    5.  Provide a **FeatureID** for your framework and primary app. You'll use these IDs to include these features in your OEMInput.xml file.

    6.  Save your updated feature manifest file.

5.  Update your OEMInput.xml file to include the new features that you defined in the previous step. For more information, see [OEMInput file contents](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/oeminput-file-contents).

    1.  Edit your OEMInput.xml file.

    2.  In the OEMInput file, locate the **OEM** group under **Features**.

    3.  Within the **OEM** group, define a feature name for the required component primary app.

        The following code example shows how to do this.

        ```XML
            <OEM>
              <Feature>CONTOSO_FRAMEWORK</Feature>
              <Feature>CONTOSO_PARTNERAPP</Feature>
            </OEM>
        ```

    4.  Change the **Feature** entries to match the **FeatureID**s for your required component and primary app.

    5.  Save your updated OEMInput file.

6.  Use the OEMInput.xml file as one of the inputs to build the mobile image.

    You can use ImgGen.cmd to build the image.

7.  Depending on the mobile image type that you built, you may need to sign the image before you can flash it to the phone. For more information, see [Sign a full flash update (FFU) image](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/sign-a-full-flash-update--ffu--image).

<a href="" id="testing"></a>**Testing**  
1.  Flash the image that contains the preloaded app to a mobile device.
2.  Set up the device.
3.  Once the device is fully set up, go to the full apps list.
4.  Verify that you can see your primary app listed with all the other apps in the device.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
