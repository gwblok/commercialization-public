---
title: OOBE.xml
description: Customization options for OOBE.xml
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/17/2017
ms.topic: article


---
# OOBE.xml

Create a file named **Oobe.xml** to organize text and images displayed during OOBE, and to specify settings for customizing the Windows 10 first-run experience. For Windows 10, you can use multiple Oobe.xml files for language- and region-specific license terms and settings so that users see appropriate info as soon as they start their PCs. By specifying information in the Oobe.xml file, you help fill in some of the required information so that users are asked to do only the core tasks required to set up their PCs.

## OOBE.xml settings

You can set the default language, location, and keyboard layout using Oobe.xml. The default values you set in Oobe.xml will be the default values the user sees on the Language, Region, and Keyboard layout selection screens during OOBE. The user can select another value from the list if desired, and their selection will override the Oobe.xml settings.

You can also specify a default timezone for the device using Oobe.xml. If the device has network connectivity during OOBE, Windows will attempt to detect the user’s time zone and this will override the value set in Oobe.xml. If the device does not have connectivity, or the user has turned off Location settings in OOBE, Windows will not be able to detect the timezone, and will default to the value you set in Oobe.xml. In this case, the user will see this timezone reflected by their clock once they reach the desktop.

For a list of time zones you can set, see [Default Time Zones](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/default-time-zones).

There are a number of other settings available to enable further customization of OOBE. See [Configure Oobe.xml](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/configure-oobexml) for information about all of the settings available to you.

## Configure OOBE.xml for multi-language and region deployments, and single-language and region deployments

You can create multiple OOBE.xml files for each language and region you intend to deploy in to provide appropriate default values in each location. For more information, see [How OOBE.xml works](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-oobexml-works).

## Oobe.xml example

```XML
<FirstExperience>
  <oobe>
    <oem>
      <name>Fabrikam</name>
      <eulafilename>eula.rtf</eulafilename>
      <computername>Fabrikam-PC</computername>
      <registration>
        <title>Register your PC</title>
        <subtitle>This page will help Fabrikam know about you.</subtitle>
        <customerinfo>
          <label>Let Fabriakm contact you</label>
          <defaultvalue>true</defaultvalue>
        </customerinfo>
        <checkbox1>
          <label>Use Contoso Antimalware to help protect your PC</label>
          <defaultvalue>true</defaultvalue>
        </checkbox1>
        <checkbox2>
          <label>Let Fabrikam send you offers</label>
        </checkbox2>
        <checkbox3>
          <label>Let Fabrikam send you offers</label>
        </checkbox3>
        <link1>
          <label>Learn more about Contoso Antimalware</label>
        </link1>
        <link2>
          <label>Learn more about Fabrikam offers</label>
        </link2>
        <link3>
          <label>Fabrikam privacy statement</label>
        </link3>
        <hideSkip>true</hideSkip>
      </registration>
    </oem>
    <defaults>
      <language>1033</language>
      <location>244</location>
      <keyboard>0409:00000409</keyboard>
      <timezone>Central Europe Daylight Time</timezone>
      <adjustForDST>true</adjustForDST>
    </defaults>
    <hidSetup>
      <title>Pair Your Fabrikam MouseKeyboard</title>
      <mouseImagePath>c:\fabrikam\mouse.png</mouseImagePath>
      <mouseErrorImagePath>c:\fabrikam\errormouse.png</mouseErrorImagePath>
      <mouseText>Pair your mouse now.</mouseText>
      <mouseErrorText>Something has gone wrong.</mouseErrorText>
      <keyboardImagePath>c:\fabrikam\keyboard.png</keyboardImagePath>
      <keyboardErrorImagePath>C:\fabrikam\errorkeyboard.png</keyboardErrorImagePath>
      <keyboardText>Now pair the keyboard.</keyboardText>
      <keyboardErrorText>Keyboard pairing did not happen.</keyboardErrorText>
      <keyboardPINImagePath>c:\fabrikam\keyboardpin.png</keyboardPINImagePath>
      <keyboardPINText>Enter the PIN for your keyboard.</keyboardPINText>
    </hidSetup>
  </oobe>
</FirstExperience>
```
