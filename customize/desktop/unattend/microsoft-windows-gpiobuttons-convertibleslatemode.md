---
title: ConvertibleSlateMode
description: ConvertibleSlateMode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 78b5f36f-fe4c-4c09-b1ba-bf8c6fafc45d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ConvertibleSlateMode


`ConvertibleSlateMode` specifies whether the device has a physical keyboard. Windows uses this setting when determining whether to show an on-screen keyboard. For example, when the user receives a prompt that can accept keyboard input on a tablet, the on-screen keyboard appears.

This setting is related to [ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md), which determines whether to prompt the user to show or hide the keyboard whenever the device changes modes, for example, when the keyboards is attached/detached or rotated to be accessible/inaccessible.

## Recommended settings


**For tablets or other devices that don’t have a keyboard**, set ConvertibleSlateMode to **0**.

**For laptops or other devices that always have an accessible keyboard**, set ConvertibleSlateMode to **1**.

**For convertible or detachable devices that sometimes have an accessible keyboard**:

-   Set ConvertibleSlateMode to **0**.
-   Set [ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md) to **1**.
-   Set up a GPIO pin and a [GPIO Injection Driver](http://go.microsoft.com/fwlink/?LinkId=320790) to detect the mode. When the mode changes, the driver should update the registry value of **HKLM/System/CurrentControlSet/Control/PriorityControl/ConvertibleSlateMode**.
-   For devices that can use Windows 10 Continuum feature, also see the topic: [Continuum](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/continuum).

**For devices without a touchscreen**, this setting does nothing. Even if you set this setting, Windows assumes a physical keyboard is present and will not show the on-screen keyboard.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Laptop mode: Specifies that the device has a physical keyboard accessible to the user.</p></td>
</tr>
<tr class="even">
<td><p>0</p></td>
<td><p>Tablet mode: Specifies that the device does not have a physical keyboard accessible to the user.</p>
<p>This is the default value</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-GPIOButtons](microsoft-windows-gpiobuttons.md) | **ConvertibleSlateMode**

## Valid Configuration Passes


specialize

offlineServicing

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-GPIOButtons](microsoft-windows-gpiobuttons.md).

## XML Example


The following XML output specifies a laptop form factor.

```
<ConvertibleSlateMode>1</ConvertibleSlateMode>
```

## Related topics


[Microsoft-Windows-GPIOButtons](microsoft-windows-gpiobuttons.md)

[ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md)

[GPIO Implementation Guide](https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/gpio-buttons-and-indicators-implementation-guide-for-windows-8-1)

[Continuum](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/continuum)

 

 







