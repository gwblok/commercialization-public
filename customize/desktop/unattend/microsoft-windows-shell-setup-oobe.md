---
title: OOBE
description: OOBE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 803193bb-87ab-405b-8bf8-a429f51cf602
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OOBE

`OOBE` specifies the behavior of some of the Windows Out of Box Experience (OOBE) screens.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[HideEULAPage](microsoft-windows-shell-setup-oobe-hideeulapage.md)|Hides the Microsoft Software License Terms page. OEMs and System Builders can use this setting only for testing prior to shipment.|
|[HideLocalAccountScreen](microsoft-windows-shell-setup-oobe-hidelocalaccountscreen.md)|Hides the Administrator password screen. This setting applies only to the Windows Server editions.|
|[HideOEMRegistrationScreen](microsoft-windows-shell-setup-oobe-hideoemregistrationscreen.md)|Hides the OEM registration page.|
|[HideOnlineAccountScreens](microsoft-windows-shell-setup-oobe-hideonlineaccountscreens.md)|Specifies whether the user will be required to sign-in during OOBE.|
|[HideWirelessSetupInOOBE](microsoft-windows-shell-setup-oobe-hidewirelesssetupinoobe.md)|Hides the Join Wireless Network page.|
|[NetworkLocation](microsoft-windows-shell-setup-oobe-networklocation.md)|Specifies the network type.|
|[OEMAppID](microsoft-windows-shell-setup-oobe-oemappid.md)|Enables the OEM to specify app information.|
|[ProtectYourPC](microsoft-windows-shell-setup-oobe-protectyourpc.md)|Hides the Help protect your computer and improve Windows automatically page. That page specifies whether updates are automatically downloaded and installed.|
|[UnattendEnableRetailDemo](microsoft-windows-shell-setup-oobe-unattendenableretaildemo.md)|Use to enable retail demo mode on the device.|
|[VMModeOptimizations](microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md)|Use to customize the user experience when in VM mode.|

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **OOBE**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML example shows how to set OOBE information for testing.

```XML
<OOBE>
   <HideEULAPage>true</HideEULAPage>
   <NetworkLocation>Other</NetworkLocation>
   <ProtectYourPC>3</ProtectYourPC>
</OOBE>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
