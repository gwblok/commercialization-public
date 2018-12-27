---
title: Microsoft-Windows-DeviceGuard-Unattend
description: The Microsoft-Windows-DeviceGuard-Unattend component specifies settings for initializing and enforcing virtualization-based security, which helps protect system memory and kernel mode apps and drivers from possible tampering.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 830235BE-16BB-4174-AF4B-0D6F5940628A
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-DeviceGuard-Unattend

The `Microsoft-Windows-DeviceGuard-Unattend` component specifies settings for initializing and enforcing virtualization-based security, which helps protect system memory and kernel mode apps and drivers from possible tampering.

Administrators can set values for the following settings to control virtualization-based security.

## In this section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [EnableVirtualizationBasedSecurity](Microsoft-Windows-DeviceGuard-Unattend-enablevirtualizationbasedsecurity.md) | Use to enable virtualization-based security. |
| [HypervisorEnforcedCodeIntegrity](Microsoft-Windows-DeviceGuard-Unattend-hypervisorenforcedcodeintegrity.md) | Specifies the code integrity that will be enforced for the hypervisor, which is a layer of software under the OS that runs virtual machines. |
| [LsaCfgFlags](Microsoft-Windows-DeviceGuard-Unattend-lsacfgflags.md) | Use to enable the Credential Guard, which uses virtualization-based security to isolate secrets so that only privileged system software can access them when they are stored on disk or in memory. For more information, see [Credential Guard](https://docs.microsoft.com/en-us/windows/access-protection/credential-guard/credential-guard). |

## XML example

The following unattend XML example shows how you can enable virtualization-based security.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="offlineServicing">
      <component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-DeviceGuard-Unattend">
         <EnableVirtualizationBasedSecurity>1</EnableVirtualizationBasedSecurity>
         <HypervisorEnforcedCodeIntegrity>1</HypervisorEnforcedCodeIntegrity>
         <LsaCfgFlags>1</LsaCfgFlags>
      </component>
   </settings>
   <cpi:offlineImage xmlns:cpi="urn:schemas-microsoft-com:cpi" cpi:source="wim:c:/install2/sources/install.wim#Windows 10 Enterprise"/>
</unattend>
```

## Enabling Device Guard or Credential Guard

In addition to the Unattend settings in `Microsoft-Windows-DeviceGuard-Unattend`, you also need to either enable Hyper-V and IUM to enable Device Guard or Credential Guard, or you can directly set registry keys using FirstLogonCommands.

* Enable Hyper-V and IUM to turn on Device Guard or Credential Guard by running the following DISM commands:
  * **DISM.EXE /Image:***&lt;full path to offline image&gt;* **/Enable-Feature:Microsoft-Hyper-V-Hypervisor /All**
  * **DISM.EXE /Image:***&lt;full path to offline image&gt;* **/Enable-Feature: IsolatedUserMode /All**
* Set the following registry keys using the [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) setting:
  * **REG ADD "HKLM\\SYSTEM\\CurrentControlSet\\Control\\DeviceGuard" /v "EnableVirtualizationBasedSecurity" /t REG\_DWORD /d 1 /f**
  * **REG ADD "HKLM\\SYSTEM\\CurrentControlSet\\Control\\Lsa" /v "LsaCfgFlags" /t REG\_DWORD /d 1 /f**
  * **REG ADD "HKLM\\SYSTEM\\CurrentControlSet\\Control\\DeviceGuard" /v "HypervisorEnforcedCodeIntegrity" /t REG\_DWORD /d 1 /f**

Read the following articles to learn more about Device Guard and Credential Guard:

* [Device Guard overview](https://docs.microsoft.com/en-us/windows/device-security/device-guard/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
* [Device Guard deployment guide](https://docs.microsoft.com/en-us/windows/device-security/device-guard/device-guard-deployment-guide)
* [Protect derived domain credentials with Credential Guard](https://docs.microsoft.com/en-us/windows/access-protection/credential-guard/credential-guard)

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
