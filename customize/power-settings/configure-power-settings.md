---
title: Configure power settings
description: This section contains information about the power settings that you can configure using the Windows provisioning framework. Each power setting topic includes the identification GUID, allowed values, meaning, and common usage scenarios for the setting.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6FA47DE6-540E-4AA9-A76E-3A02025B5C58


ms.date: 11/13/2018
ms.topic: article


---
# Configure power settings

This section contains information about the power settings that you can configure using the Windows provisioning framework. Each power setting topic includes the identification GUID, allowed values, meaning, and common usage scenarios for the setting.

> [!Tip]
> The primary audience for these topics is Original Equipment Manufacturers (OEMs). If you're a Windows device owner (consumer) and would like to learn more about power settings in Windows 10, please see [How to enable Hibernate and Sleep in Power Options](https://answers.microsoft.com/en-us/insider/forum/insider_wintp-insider_personal/how-to-enable-hibernate-and-sleep-in-power-options/2bca761d-a35a-4d07-9e7b-dc2c8f2330b3) on Microsoft's community support site. You can also search for troubleshooting instructions on this site if needed.

## Use Windows Configuration Designer to configure power settings

To configure the power settings, you will first create a provisioning package using [Windows Configuration Designer](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-install-icd). You will then edit the customizations.xml file contained in the package to include your power settings. Use the XML file as one of the inputs to the Windows Configuration Designer command-line to generate either a provisioning package or a Windows image that contains the power settings. For information on how to use the Windows Configuration Designer CLI, see [Use the Windows Configuration Designer command-line interface](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-command-line).

The power settings are not visible in the Windows Configuration Designer UI but appear under the main `Common\Power` namespace. This namespace is further divided into various groups including:

* `Policy\Settings` which includes the following subgroups:
  * `AdaptivePowerBehavior`
  * `Processor`
  * `Battery`
  * `Button`
  * `Display`
  * `Disk`
  * `EnergySaver`
  * `PCIExpress`
  * `Sleep`
  * `Misc`

* `Controls\Settings` which includes the following settings:
  * `LidNotificationsAreReliable`
  * `EnableInputSuppression`
  * `IgnoreCsComplianceCheck`

The following example shows what your Windows provisioning answer file might look like after you've written it.

```XML
<?xml version="1.0" encoding="utf-8"?>
<WindowsCustomizatons>
  <PackageConfig xmlns="urn:schemas-Microsoft-com:Windows-ICD-Package-Config.v1.0">
    <ID>{7e5c6cb3-bd16-4c1a-aacb-98c9151d5f20}</ID>  <!-- ID needs to be be unique GUID for the package -->
    <Name>CustomOEM.Power.Settings.Control</Name>
    <Version>1.0</Version>
    <OwnerType>OEM</OwnerType>
  </PackageConfig>

  <Settings xmlns="urn:schemas-microsoft-com:windows-provisioning">
    <Customizations>
      <Common>
          <Power>
            <Policy>
              <Settings>
                <Sleep>
                  <SchemePersonality>
                    <Default SchemeAlias="Balanced">
                      <Setting>
                      <!-- Duration of time after sleep that the system automatically wakes and 
                           enters hibernate in seconds -->
                         <HibernateTimeout> 
                          <AcValue>1800</AcValue> <!-- 30 minutes -->
                          <DcValue>1800</DcValue> <!-- 30 minutes -->
                        </HibernateTimeout>
                      </Setting>
                    </Default>
                   </SchemePersonality>
                 </Sleep>
                 <Misc>
                   <SchemePersonality>
                     <Default SchemeAlias="Balanced">
                       <Setting>
                       <!-- Enables/Disables only WiFi connection during standby -->
                         <AllowWifiInStandby>
                           <AcValue>0</AcValue>
                           <DcValue>0</DcValue>
                         </AllowWifiInStandby>
                       </Setting>
                     </Default>
                   </SchemePersonality>
                  </Misc>
             </Settings>
           </Policy>
        </Power>
      </Common>
    </Customizations>
  </Settings>
</WindowsCustomizatons>
```

## Use Powercfg.exe to control power schemes

You can use the powercfg.exe tool to control power schemes by providing the GUID or alias for the setting. For more information on how to use this tool, see [Powercfg command-line options](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options).

## In this section

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="adaptive-hibernate.md" data-raw-source="[Adaptive hibernate](adaptive-hibernate.md)">Adaptive hibernate</a></p></td>
<td><p>Adaptive hibernate supports triggers which eliminate resume to a dead battery, and provide a great Modern Standby experience by ensuring that the system remains in CS for as long as possible.</p></td>
</tr>
<tr class="even">
<td><p><a href="power-controls.md" data-raw-source="[Power controls](power-controls.md)">Power controls</a></p></td>
<td><p>Settings in this subgroup include settings that control the system&#39;s power and behavior.</p></td>
</tr>
<tr class="odd">
<td><p><a href="configure-processor-power-management-options.md" data-raw-source="[Processor power management options](configure-processor-power-management-options.md)">Processor power management options</a></p></td>
<td><p>The Windows 10 processor power management (PPM) algorithms implement OS-level functionality that allows the OS to efficiently use the available processing resources on a platform by balancing the user&#39;s expectations of performance and energy efficiency.</p></td>
</tr>
<tr class="even">
<td><p><a href="battery-settings.md" data-raw-source="[Battery settings](battery-settings.md)">Battery settings</a></p></td>
<td><p>Settings in this subgroup control the customization of battery actions and thresholds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="power-button-and-lid-settings.md" data-raw-source="[Power button and lid settings](power-button-and-lid-settings.md)">Power button and lid settings</a></p></td>
<td><p>Settings in this subgroup control the customization of system button actions.</p></td>
</tr>
<tr class="even">
<td><p><a href="display-settings.md" data-raw-source="[Display settings](display-settings.md)">Display settings</a></p></td>
<td><p>Settings in this subgroup control the power management of the display.</p></td>
</tr>
<tr class="odd">
<td><p><a href="disk-settings.md" data-raw-source="[Disk settings](disk-settings.md)">Disk settings</a></p></td>
<td><p>Settings in this subgroup control the power management of disk devices.</p></td>
</tr>
<tr class="even">
<td><p><a href="energy-saver-settings.md" data-raw-source="[Energy Saver settings](energy-saver-settings.md)">Energy Saver settings</a></p></td>
<td><p>Settings in this subgroup control the battery threshold and brightness when Energy Saver is turned on.</p></td>
</tr>
<tr class="odd">
<td><p><a href="pci-express-settings.md" data-raw-source="[PCI Express settings](pci-express-settings.md)">PCI Express settings</a></p></td>
<td><p>Settings in this subgroup control the power management of PCI Express links.</p></td>
</tr>
<tr class="even">
<td><p><a href="sleep-settings.md" data-raw-source="[Sleep settings](sleep-settings.md)">Sleep settings</a></p></td>
<td><p>Settings in this subgroup control sleep, resume, and other related functionality.</p></td>
</tr>
<tr class="odd">
<td><p><a href="no-subgroup-settings.md" data-raw-source="[Other power settings](no-subgroup-settings.md)">Other power settings</a></p></td>
<td><p>Settings in this subgroup do not belong to any other subgroup.</p></td>
</tr>
<tr class="even">
<td><p><a href="legacy-configuration-options.md" data-raw-source="[Legacy configuration options](legacy-configuration-options.md)">Legacy configuration options</a></p></td>
<td></td>
</tr>
</tbody>
</table>
