---

Description: 'Boot to a virtual hard disk: Add a VHDX or VHD to the boot menu'
ms.assetid: e00d7f8f-502c-40e5-904c-8cc653c1899e
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Boot to a virtual hard disk: Add a VHDX or VHD to the boot menu'

ms.date: 01/24/2018
ms.topic: article


---

# Boot to a virtual hard disk: Add a VHDX or VHD to the boot menu

Native Boot allows you to create a virtual hard disk (VHDX), install Windows to it, and then boot it up, either on your PC side-by-side with your existing installation, or on a new device.

A native-boot VHDX can be used as the running operating system on designated hardware without any other parent operating system. This differs from a scenario where a VHDX is connected to a virtual machine on a computer that has a parent operating system.

Native boot for Windows 10 requires the **.vhdx** format, not the .vhd format.

VHDXs can be applied to PCs or devices that have no other installations of Windows, without a virtual machine or hypervisor. (A hypervisor is a layer of software under the operating system that runs virtual computers.) This enables greater flexibility in workload distribution because a single set of tools can be used to manage images for virtual machines and designated hardware.

You can also deploy the VHDX to a PC that already has Windows installed on it, and use a boot menu to select between the existing version of Windows, or the version on the VHD.

To learn more about using VHDXs in an enterprise environment, see [Understanding Virtual Hard Disks with Native Boot](understanding-virtual-hard-disks-with-native-boot.md).

## <span id="Prerequisites"></span>Prerequisites


-   A technician PC with the Windows Assessment and Deployment Kit (Windows ADK) tools installed on it.

-   A generalized Windows image (.WIM file). To learn more, see [Sysprep (Generalize) a Windows installation](sysprep--generalize--a-windows-installation.md).

-   A bootable Windows PE drive. To learn more, see [WinPE: Create USB Bootable drive](winpe-create-usb-bootable-drive.md).

-   A destination PC or device on which to install the VHDX. This device requires 30 gigabytes (GB) or more of free disk space. You can install the VHDX to a device already running other operating system installations, or as the only operating system on a device.

## <span id="Step_1__Create_a_VHD_from_diskpart">Step 1: Create a VHDX from diskpart

On the technician PC:

1.  From the Command Prompt, open Diskpart.

    ``` 
    diskpart
    ```

2.  Create and prepare a new VHDX. In this example, we create a 25 GB fixed-type VHDX.

    ``` 
    create vdisk file=C:\windows.vhdx maximum=25600 type=fixed
    ```

3.  Attach the VHDX. This adds the VHDX as a disk to the storage controller on the host.

    ``` 
    attach vdisk
    ```

4.  Create a partition for the Windows files, format it, and assign it a drive letter. This drive letter will appear in File Explorer.

    ``` 
    create partition primary
    format quick label=vhdx
    assign letter=v
    ```

5.  Exit Diskpart

    ``` 
    exit
    ```

## <span id="Step_2__Apply_a_Windows_image_to_the_VHD">Step 2: Apply a Windows image to the VHD

On your technician PC, apply a generalized Windows image to the primary partition of the VHDX that you created and attached in [Step 1](#Step_1__Create_a_VHD_from_diskpart).

```
Dism /Apply-Image /ImageFile:install.wim /index:1 /ApplyDir:V:\
```

## <span id="Step_3__Detach_the_VHD__copy_it_to_a_new_device__and_attach_it__optional_">Step 3: Detach the VHD, copy it to a new device, and attach it (optional)


You can deploy the VHDX to a device that already has a copy of Windows installed on it, or you can clean and prepare the destination PC's hard drive to use the VHD.

**Detach the VHDX and save it to a network share or storage drive**


1.  Use diskpart to detach the virtual disk from your technician PC.

    ``` 
    diskpart
    select vdisk file=C:\windows.vhdx
    detach vdisk
    exit
    ```

2.  Copy the VHDX to a network share or removable storage drive. The following maps a drive letter to a network share, creates a directory for the VHD, and then copies the VHD.

    ``` 
    net use n: \\server\share\
    md N:\VHDs
    copy C:\windows.VHDX n:\VHDs\
    ```

**Clean and prepare a new device for native boot**

On your destination PC:
1.  Use your bootable WinPE key to [boot the destination PC to WinPE](boot-to-uefi-mode-or-legacy-bios-mode.md).
2.  Clean and prepare the destination PC's hard drive. Create a system partition (S), and a main partition (M) where the VHDX will be stored.

    BIOS:

    ``` 
    diskpart
    select disk 0
    clean
    rem == 1. System partition ======================
    create partition primary size=100
    format quick fs=ntfs label="System"
    assign letter="S"
    active
    rem == 2. Main partition ========================
    create partition primary
    format quick fs=ntfs label="Main"
    assign letter="M"
    exit
    ```

    UEFI:

    ```
    diskpart
    select disk 0
    clean
    convert gpt
    rem == 1. System partition =========================
    create partition efi size=100
    format quick fs=fat32 label="System"
    assign letter="S"
    rem == 2. Microsoft Reserved (MSR) partition =======
    create partition msr size=128
    rem == 3. Main partition ===========================
    create partition primary 
    format quick fs=ntfs label="Main"
    assign letter="M"
    exit
    ```

3.  Connect to the network drive or storage location where you copied the VHDX in [step 3.2](#Step_3__Detach_the_VHD__copy_it_to_a_new_device__and_attach_it__optional_). 

    ``` 
    net use N: \\server\share
    ```

4.  Copy the VHDX from the network drive or storage location to the destination PC's main partition.

    ``` 
    copy N:\VHDs\Windows.vhdx M:
    ```

**Attach the VHDX**

1.  While still booted into WinPE, attach your VHDX to the destination PC.

    ```
    diskpart
    select vdisk file=M:\windows.vhdx
    attach vdisk
    ```

2.  Identify the attached VHDX's volume letter. (Optional: Change it to another letter that makes more sense, for example V, and leave the diskpart command line open for the next step).

    ```
    list volume
    select volume 3
    assign letter=v
    ```

## <span id="Step_4__Add_a_boot_entry"></span>Step 4: Add a boot entry


1.  From your destination PC, open Diskpart (if necessary) and identify the drive letters of the VHDX and the system partition, for example, V and S.

    ``` 
    diskpart
    list volume
    exit
    ```

2.  Add a boot entry to the device. You can add multiple VHDX files using this method.

    BIOS:

    ``` 
    V:
    cd v:\windows\system32
    bcdboot v:\windows /s S: /f BIOS
    ```

    UEFI:

    ``` 
    V:\
    cd v:\windows\system32
    bcdboot v:\windows /s S: /f UEFI
    ```

3.  Remove the Windows PE USB key.

4.  Restart the destination PC.

    If there's only one boot entry, the device immediately boots to Windows. If there's more than one boot entry, you'll see a boot menu where you can choose between the available versions of Windows on the device.

## <span id="related_topics"></span>Related topics


[Understanding Virtual Hard Disks with Native Boot](understanding-virtual-hard-disks-with-native-boot.md)

[BCDboot Command-Line Options](bcdboot-command-line-options-techref-di.md)