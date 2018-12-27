---
title: Customize SIM card slot names
description: Customize the names of SIM card slots on the device. The names you choose are displayed in Settings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 04/30/2018
ms.topic: article
ms.custom: RS5
---
# Customize SIM card slot names

In Windows 10, version 1803, you can customize the names of SIM card slots on the device to more easily differentiate between them. For example, if the device has both an embedded SIM slot and an external SIM slot, customizing the names will help your customers understand which is which.

> [!Important]
> Only devices with a Dual SIM Single Activation (DSSA) configuration support this customization.

The SIM card slot names that you choose are displayed in **Settings**, under **Network & Internet** > **Cellular**. If no custom names are provided, the default names are **SIM1** and **SIM2**.

## Instructions

1. Create a provisioning XML file (prov.xml). For instructions, see [Create a Prov.xml](https://msdn.microsoft.com/en-us/library/dn499756.aspx).
1. Add the following XML to your provisioning XML file:

   ```XML
    <wap-provisioningdoc>
        <characteristic type="Registry">
            <characteristic type="HKLM\Software\Microsoft\Cellular\MVSettings\DeviceSpecific\CellUX">
                <parm name="SlotSelectionSim1Name" value="Your SIM name 1" datatype="string"/>
                <parm name="SlotSelectionSim1Name" value="Your SIM name 2" datatype="string"/>
            </characteristic>
        </characteristic>
    </wap-provisioningdoc>
   ```

1. Replace "Your SIM name 1" and "Your SIM name 2" with the desired names for your SIM card slots.
1. Create a resource-only .dll for the localized versions of your SIM card slot names. See [Create a resource-only .dll for localized strings](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/create-a-resource-only-dll-for-localized-strings) for instructions.
1. In your resource-only .dll, set the `BaseD11` asset to point to the location of your base MUI DLL file. For example: `C:\Path\DisplayStrings.dll`.
1. Add the language MUI packages (*.dll.mui) for all the languages you are supporting and have localized strings for. To do this:
   * Set the asset's `Name` to `LanguageDll/$(langid)` where `$(langid)` corresponds to the language. For example: `LanguageDll/en-US`.
   * Set the asset's `Source` to the location of the .dll.mui file for that language. For example: `C:\Path\en-us\DisplayStrings.dll.mui`.
   * Repeat these steps for other languages. For example, the following XML has entries for en-US, fr-CA, and es-MX languages.

   ```XML
   <Asset Name="LanguageDll/en-US" Source="C:\Path\en-us\DisplayStrings.dll.mui" />
   <Asset Name="LanguageDll/fr-CA" Source="C:\Path\fr-CA\DisplayStrings.dll.mui" />
   <Asset Name="LanguageDll/es-MX" Source="C:\Path\es-MX\DisplayStrings.dll.mui" />
   ```

## Related topics

[Create a resource-only .dll for localized strings](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/create-a-resource-only-dll-for-localized-strings)

[Customizations for mobile devices](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/windows-10-mobile-customizations-portal)
