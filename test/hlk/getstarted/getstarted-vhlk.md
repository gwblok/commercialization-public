---
title: VHLK Getting Started Guide
description: Information and Guidance for the Windows Virtual Hardware Lab Kit (VHLK)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/02/2018
ms.topic: article
ms.custom: RS5
---

# Getting started with the Windows Virtual Hardware Lab Kit (VHLK)

The Windows Virtual Hardware Lab Kit (VHLK) is an HLK Controller pre-configured on a VHD that can be booted as a VM in Hyper-V. The VHLK includes an Evaluation copy of Windows Server 2016, and can be downloaded from the [Microsoft Eval Center](https://www.microsoft.com/en-us/evalcenter/evaluate-virtual-hardware-lab-kit) 

>[!WARNING]
>After booting the VHLK, do not change the auto-generated computer name (i.e. WIN-xxxx).

>[!NOTE]
>Generation 2 VM's are not supported by the VHLK

>[!NOTE]
>Default login credentials are HLKAdminUser with password Testpassword,1

## Physical (Host) Machine Specifications
Recommended:

- 8-core, 64-bit processor with SLAT
- 8GB RAM
- Virtualization support turned on in BIOS / UEFI
- 120GB HDD free space

## Virtual Machine Settings
Recommended:

- Memory: >= 4096MB
- Processor: >= 2 Virtual processors

## Hyper-V Setup Guide
1. [Enable Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)
2. Create a new external virtual switch
    * If you enable Hyper-V through Server Manager on Server 2016, it will prompt you to create a virtual switch
    * Otherwise follow [these instructions](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/get-started/create-a-virtual-switch-for-hyper-v-virtual-machines)
3. Obtain a local copy of the VHLK from the [Microsoft Eval Center](https://www.microsoft.com/en-us/evalcenter/evaluate-virtual-hardware-lab-kit) 
4. Create a new virtual machine in Hyper-V
    * Create a name for the VM and select 'Next'
    * Select Generation 1 and select 'Next'
    * Use 4096MB or more of startup memory and select 'Next'
    * Select a network adapter and select 'Next' (This is generally the virtual switch create above)
    * Select "Use an existing virtual hard disk" and browse for the local HLK VHDX
    * Select Finish
5. Edit Virtual Machine settings
    * Change processor to use at least 2 virtual processors 
    * Modify other settings as needed
6. Start up the VM
7. Windows will boot up and automatically create an Administrator user named HLKAdminUser with password ‘Testpassword,1’. Log in.
8. The VM will then run some HLK setup on first boot
    * Please wait for all cmd windows to finish before using the HLK 
    * Note: Occasionally the screen will be all black before this. The VM is still running, it just sometimes takes a bit for the desktop to load if the VM is not using the recommended settings.
    * **Do not rename the VM. If you change the computer name, you will not be able to connect to the HLK Controller.**
9. Once all the cmd windows have finished, you may wish to change the date/time settings.
    * By default, the server is set to "(UTC) Coordinated Universal Time", with "Set time zone automatically" and "Adjust for daylight savings time automatically" turned OFF. This may cause confusion when trying to align time stamps of various client / controller logs. To change:
        1. Click on the Date/Time section of the taskbar
        2. Select "Date and Time Settings" from the bottom of the flyout
        3. Specify the time zone you are in from the dropdown
        4. turn on "Adjust for daylight savings time automatically" (if you wish)
    * Time should now be synchronized with the various client devices and host machines.
10. At this point you are finished, and the VHLK is ready to use.

## Configuring Network Settings
On all systems, network discovery, and file sharing must be turned on. Occasionally, domain-joining a system will default these settings to off.

1. Control Panel (icon view) -> Network and Sharing Center
2. Go to "Change advanced sharing settings"
3. On the current profile, set "Turn on network discovery", and "Turn on file and printer sharing"
4. Verify these settings on the host system, virtual machine, and all desktop client systems. **Verify these settings after any network change**

When properly set up, the host system, virtual machine, and all client systems should be able to ping each other by **both IP address and name.**
