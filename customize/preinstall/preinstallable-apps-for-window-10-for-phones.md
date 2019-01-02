---
title: Preinstallable apps for mobile devices
description: Learn how to add an app to a mobile image that will be available to customers at first boot.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5d855c2c-2e2d-4fb3-b119-3998b1b6b934


ms.date: 05/02/2017
ms.topic: article


---
# Preinstallable apps for mobile devices

## <a href="" id="to-add-a-preinstalled-app-to-a-mobile--image"></a>To add a preinstalled app to a mobile image

The process for creating a preinstallable app is similar to that of a standard app. In the Windows 10 Dev Center, a developer submits an app that you want to preinstall on your Windows 10 Mobile image. Once the app is submitted, you can request a preinstallation package, download it, and add it to the image, as described in this topic.

To add a preinstallable app, you will need to perform the following actions:

* Request a preinstallation package
* Create a .provxml for the preinstallable app
* Add the app to the image with Customization answer file
* Build the image

For more information about customization answer files, see [Customization answer file](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file). For more information about building with Customization answer files, see [Building a mobile image using ImgGen.cmd](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/building-a-phone-image-using-imggencmd).

## Request a preinstallation package

Developers who have added an app to the Dev Center can request a preinstallation package for it. They can then give the preinstallation package directly to the OEM they are working with. If you are the OEM adding this application to your OS image, you would ask the developer of the application to download the application package and then give you the downloaded zip file. You cannot access their developer account directly. Once you have the preinstall package, you can continue with the rest of the steps. For more information on how a developer generates preinstall packages for an OEM, see [Generate preinstall packages for OEMs](https://docs.microsoft.com/en-us/windows/uwp/publish/generate-preinstall-packages-for-oems).

## Create a .provxml file for a preinstallable app

Adding a preinstalled app to an Windows 10 Mobile OS image requires a .provxml configuration file that specifies the installation parameters and the Windows 10 Store catalog identifiers. Specifically, it should specify the path to the .appx file, the path to the license file, and the Store catalog IDs. This information is used when the app connects to the Store service to check for updates. To minimize the chance of error, the developer portal provides the appropriate XML for your app. The following is an example of what the .provxml might look like.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<wap-provisioningdoc>
   <characteristic type="AppInstall">
      <characteristic type="AppXPackage">
         <parm name="ProductID" value="{09f2d20a-7076-4970-80ac-1bc24c171d2e}"/>
         <parm name="AppXPath" value="c:\Programs\CommonFiles\Xaps\SampleApp.appx"/>
         <parm name="LicensePath" value="c:\Programs\CommonFiles\Xaps\SampleAppLicense.xml"/>
         <parm name="InstanceID" value="{03e9a435-3000-11db-89ca-0019b92FFFFF}"/>
         <parm name="OfferID" value="{03e9a435-3000-11db-89ca-0019b92FFFFF}"/>
         <parm name="PayloadID" value="{03e9a435-3000-11db-89ca-0019b92FFFFF}"/>
         <parm name="UninstallDisabled" value="false"/>
         <parm name="FullyPreInstall" value="false"/>
         <parm name="ForceUpdate" value="false"/>
      </characteristic>
   </characteristic>
</wap-provisioningdoc>
```

> [!Note]
> provxml files for preinstalled apps must follow a prescribed naming convention. You must use MPAP\_name\_index.provxml, where name and index can be any strings. Typically, name is the name of the update package that contains the preinstalled app, and index is a string that differentiates provxml files that have the same name. Often, index is represented as a number, such as 01.

### provxml flags

These are the flags you can use in your provxml.

| Flag                                  | Description                                                                          |
|:--------------------------------------|:-------------------------------------------------------------------------------------|
| UninstallDisabled                     | This flag controls whether a preinstalled app can be uninstalled by a user. When set to FALSE(default), a user is able to uninstall the preinstalled app. When set to TRUE, a user is not able to uninstall the app. This flag is only settable via provxml and cannot be overridden through a Store update. Only a device update with an updated provxml file can change this value. Ideally, to maintain the user experience, this flag should only be set to TRUE for apps that are critical to phone functionality.                                             |
| ForceUpdate                           | This flag allows an app in an OS update image to attempt to overwrite an existing version of the app already installed on the phone prior to update to Windows 10 Mobile. The default value for this flag is FALSE. Be aware that because the app update is forced, setting this flag to TRUE might result in a downgrade in functionality if the already-installed app was developed for an earlier version of the OS. In general, this flag should only be used when the Windows 10 Mobile version of the app must be on the phone immediately after update, even if it means downgrading the version of the app already installed.                                                                          |
| FullyPreinstall                       | This flag controls whether the app is MDIL bound during first boot/update or whether it is delayed until after those operations complete. Delaying MDIL binding, which is the default behavior for apps that are not pre-pinned to Start, allows the user to get back to their phone as quickly as possible. When binding is deferred till after first boot/update completes the app icon will display greyed out with a status of “installing” and cannot be run until the deferred bind completes. The amount of time it takes to complete all deferred bindings is dependent on the number of deferred preloaded apps and the user’s activity. The flag behavior is as follows: <br/> <ul><li>**true**: MDIL binding occurs before first boot or update completes.</li> <li>**false**: If the app is pre-pinned to Start, MDIL binding is performed before first boot or update completes. If the app is not pre-pinned to Start, MDIL binding is deferred until after first boot or update completes. </li></ul> Generally, this value should be left as the default (FALSE) unless the app must be available to run immediately after first boot or an OS update. Some example situations where this flag should be set to TRUE are the following: <br/> <ul><li>OEM extension apps </li>Phone dialer-installed apps </li> <li>OEM service agents </li> Critical system settings apps</li></ul>    |

## Add the app to the image

Preinstalling apps are added to the OS image using a customizations.xml answer file. To create the customizations.xml answer file, first [install the Windows Configuration Designer](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-install-icd), and then [create a provisioning package](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-create-package). You can then open the project folder to find the customizations.xml file.

To include preinstalled apps in your image, you must add the `Application` element to your customizations.xml file with the appropriate defining attributes. The following code sample illustrates how an app would be added to a customization answer file for preinstalling.

```xml
    <Applications>
      <Application License="$(CAFE_OUTPUT_DIR)\content\App_MobileTV_7e7cc86e_e1c0_476a_ac88_db3c9ffffabb\MobileTV_License.xml" ProvXML="$(CAFE_OUTPUT_DIR)\content\App_MobileTV_7e7cc86e_e1c0_476a_ac88_db3c9ffffabb\MPAP_MobileTV_01.provxml" Source="$(CAFE_OUTPUT_DIR)\content\App_MobileTV_7e7cc86e_e1c0_476a_ac88_db3c9ffffabb\MobileTV.xap"/>
      <Application License="$(CAFE_OUTPUT_DIR)\content\App_AudioSettings_373cb76e_7f6c_45aa_8633_b00e85c73261\audio_License.xml" ProvXML="$(CAFE_OUTPUT_DIR)\content\App_AudioSettings_373cb76e_7f6c_45aa_8633_b00e85c73261\MPAP_audio_01.provxml" Source="$(CAFE_OUTPUT_DIR)\content\App_AudioSettings_373cb76e_7f6c_45aa_8633_b00e85c73261\audio.appx"/>
      <Application License="$(CAFE_OUTPUT_DIR)\content\App_MicrosoftHealthApp_0168b504_ca18_46b8_b60a_0f6fdc271c81\MicrosoftHealthApp_License.xml" ProvXML="$(CAFE_OUTPUT_DIR)\content\App_MicrosoftHealthApp_0168b504_ca18_46b8_b60a_0f6fdc271c81\MPAP_MicrosoftHealthApp_01.provxml" Source="$(CAFE_OUTPUT_DIR)\content\App_MicrosoftHealthApp_0168b504_ca18_46b8_b60a_0f6fdc271c81\MicrosoftHealthApp.appxbundle"/>
    </Applications>
```

> [!Note]
> The provxml file must be placed in the "$(runtime.commonfiles)\\Provisioning\\OEM" directory. The license file and app package (.xap or .appx) must be placed in the "$(runtime.commonfiles)\\xaps" directory

After you've configured your customizations.xml answer file, build the image using the Windows Configuration Designer command-line interface. See [Windows Configuration Designer command-line interface](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-command-line) for instructions.

## Build the image

Follow the steps in the [Build a customized mobile image using imggen](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/build-a-customized-mobile-image-using-imggen)
