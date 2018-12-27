---
title: ConvertibleSlateModePromptPreference
description: Configure ConvertibleSlateModePromptPreference to support prompts triggered by changes to ConvertibleSlateMode. OEMs must make sure that ConvertibleSlateMode is always accurate for their devices.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ED60A61B-9A9F-4245-8241-47A636A96FA3
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ConvertibleSlateModePromptPreference


Configure `ConvertibleSlateModePromptPreference` to support prompts triggered by changes to [ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md). OEMs must make sure that `ConvertibleSlateMode` is always accurate for their devices.

OEMs can configure `ConvertibleSlateModePromptPreference` to support Continuum, which is a new, adaptive user experience in Windows 10 that optimizes the look and behavior of apps and the Windows UI for a given physical form factor and the customer's usage preferences. OEMs can also configure their devices to boot straight into tablet mode using [SignInMode](microsoft-windows-shell-setup-signinmode.md). In addition, OEMs may also specify the device form factor by setting [DeviceForm](microsoft-windows-deployment-deviceform.md). For more information about Continuum, partners can download the "Windows 10 Continuum whitepaper" through the Microsoft Connect site.

To make this setting work, set up a GPIO pin and a [GPIO Injection Driver](http://go.microsoft.com/fwlink/?LinkId=320790) to detect the mode. When the mode changes, the driver should update the registry value of **HKLM/System/CurrentControlSet/Control/PriorityControl/ConvertibleSlateMode**.

For devices that can use Windows 10 Continuum feature, also see the topic: [Continuum](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/continuum).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Disable prompting</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enable prompting</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

offlineServicing

generalize

specialize

auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **ConvertibleSlateModePromptPreference**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## Related topics


[Microsoft-Windows-GPIOButtons](microsoft-windows-gpiobuttons.md)

[ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md)

[SignInMode](microsoft-windows-shell-setup-signinmode.md)

[DeviceForm](microsoft-windows-deployment-deviceform.md)

[GPIO implementation guide](https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/gpio-buttons-and-indicators-implementation-guide-for-windows-8-1)

[Continuum](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/continuum)

 

 







