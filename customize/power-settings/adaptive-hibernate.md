---
title: Adaptive Hibernate
description: Adaptive hibernate provides triggers to allow the system to hibernate intelligently.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1D38C059-9D2A-46BC-A457-90361240457A


ms.date: 10/17/2017
ms.topic: article


---
# Adaptive hibernate

Users can set the Hibernate option in their Windows devices to put the system into a low power state when the system is not in use. The current logic for hibernate relies on an OEM- or user-configured doze to hibernate timer. The most common timer value is 4 hours. A fixed doze to hibernate timer may offer a consistent and predictable user experience, however it doesn’t address rapid drain of battery.

The timer-based logic has some significant user experience drawbacks. A fixed doze timer can result in the system fully draining the battery in standby if it happened within the doze timeout or cut short a Modern Standby experience by hibernating at doze timeout. The timer is generally not the best option when it comes to addressing the worst case battery drain and the system needs to be adaptive and hibernate based on battery drain and user needs.

Adaptive hibernate provides triggers which allow the system to hibernate intelligently. These triggers provide the following benefits:

* Eliminate resuming to a dead battery.
* Provide a great [Modern Standby](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/modern-standby) (MS) experience by ensuring that the system remains in MS for as long as possible.

To support the adaptive hibernate triggers, the system is enabled with default values. However, OEMs can program these triggers to ensure that machines hibernate to provide the best possible experience to users.

## System requirements

The triggers apply to Modern Standby systems only.

## Default behavior

Machines will have adaptive hibernate timeout enabled by default; however, OEMs can configure the settings using a provisioning package file. See the following sections for more information on how to do this.

## Hibernate triggers

Adaptive hibernate settings (standby budget setting and standby reserve time setting) are exposed as hidden power settings. The settings are applied on DC only and have no impact on AC.

### Standby budget setting

The following table lists the settings you can use to set the standby budget, which is the amount of battery the user is allowed to drain during standby.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Budget setting</th>
<th>Definition</th>
<th>Exposed as</th>
<th>Powercfg command</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="standbybudgetpercent.md" data-raw-source="[StandbyBudgetPercent](standbybudgetpercent.md)">StandbyBudgetPercent</a></p></td>
<td><p>Defines the battery drain % that the user is allowed in a standby session. Default is 5%.</p></td>
<td><p>Power setting</p></td>
<td><p><code>powercfg /setdcvalueindex scheme_current sub_presence standbybudgetpercent</code></p></td>
</tr>
</tbody>
</table>

You can also configure these settings using a custom provisioning package file for OEM images. For more information about powercfg, see [Powercfg command-line options](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options).

### Standby reserve time setting

Reserve time is the amount of time the user is guaranteed to have the screen on after the system resumes from standby or hibernate. The following table lists the settings you can use to set the reserve time.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Budget setting</th>
<th>Definition</th>
<th>Exposed as</th>
<th>Powercfg command</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="standbyreservetime.md" data-raw-source="[StandbyReserveTime](standbyreservetime.md)">StandbyReserveTime</a></p></td>
<td><p>Defines the screen on time, in seconds, that will be available to the user after standby exits and the screen turns on. Default is 1200 seconds.</p></td>
<td><p>Power setting</p></td>
<td><p><code>powercfg /setdcvalueindex scheme_current sub_presence standbyreservetime</code></p></td>
</tr>
</tbody>
</table>

You can also configure these settings using a custom provisioning package file for OEM images. For more information about powercfg, see [Powercfg command-line options](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options).

## <span id="Windows_provisioning_package_sample"></span><span id="windows_provisioning_package_sample"></span><span id="WINDOWS_PROVISIONING_PACKAGE_SAMPLE"></span>Windows provisioning package sample

You can use the Windows Provisioning framework to configure the adaptive hibernate settings described in this section. First, create a provisioning package using [Windows Configuration Designer](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-install-icd). You will then edit the customizations.xml file contained in the package to include your power settings, which appear under the `Common\Power\Policy\Settings\AdaptivePowerBehavior` namespace. Use the XML file as one of the inputs to the Windows Configuration Designer command-line interface to generate either a provisioning package that contains the power settings. You can then apply the provisioning package to the image. For information on how to use the Windows Configuration Designer CLI, see [Use the Windows Configuration Designer command-line interface](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-command-line).

The following example shows what your Windows provisioning answer file might look like after you've written it to configure adaptive hibernate settings.

```XML
<?xml version="1.0" encoding="utf-8"?>
<WindowsCustomizatons>
  <PackageConfig xmlns="urn:schemas-Microsoft-com:Windows-ICD-Package-Config.v1.0">
    <ID>{XXXX GUID}</ID>  <!-- ID needs to be be unique GUID for the package -->
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
                    <AdaptivePowerBehavior>
                       <SchemePersonality>
                          <Default SchemeAlias="Balanced">
                             <Setting>
                                <!-- After entering standby, battery drain percentage allowed before the device transitions to hibernate -->
                                <StandbyBudgetPercent>
                                   <DcValue>3</DcValue>
                                </StandbyBudgetPercent>
                                <!-- After entering standby, number of seconds before the device automatically transitions to hibernate -->
                                <StandbyReserveTime>
                                   <DcValue>600</DcValue>
                                </StandbyReserveTime>
                             </Setting>

                          </Default>
                       </SchemePersonality>
                    </AdaptivePowerBehavior>
                 </Settings>
              </Policy>
           </Power>
        </Common>
     </Customizations>
  </Settings>
```

## <span id="User_prediction"></span><span id="user_prediction"></span><span id="USER_PREDICTION"></span>User prediction

User usage prediction no longer triggers Hibernate. This is a change from previous versions of Windows. Windows continues to support automatically transitioning from Hibernate back to Modern Standby based on user prediction, however this requires that the device implement RTCWake or the Time & Device Alarm object in ACPI.
