---

Description: Understanding Virtual Hard Disks with Native Boot
ms.assetid: e063e475-6f39-4ed9-9473-ea7537adc30a
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Understanding Virtual Hard Disks with Native Boot
redirect_url: https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/deploy-windows-on-a-vhd--native-boot

ms.date: 01/24/2018
ms.topic: article


---

# Understanding Virtual Hard Disks with Native Boot


Native boot enables Windows 10 virtual hard disks (VHDXs) to run on a computer without a virtual machine or *hypervisor*. A hypervisor is a layer of software under the operating system that runs virtual machines. Native boot for Windows 10 requires the .vhdx format, not the .vhd format.

## <span id="BKMK_whatIsVHD"></span><span id="bkmk_whatisvhd"></span><span id="BKMK_WHATISVHD"></span>What Is VHD with Native Boot?


A virtual hard disk can be used as the running operating system on designated hardware without any other parent operating system, virtual machine, or hypervisor. Windows disk-management tools, the DiskPart tool and the Disk Management Microsoft Management Console (Diskmgmt.msc), can be used to create a VHD file. A supported Windows image (.wim) file can be applied to a VHD, and the VHD can be copied to multiple systems. The Windows boot manager can be configured to boot directly into the VHD.

The VHD can also be connected to a virtual machine for use with the Hyper-V Role in Windows Server.

Native-boot VHDs are not designed or intended to replace full image deployment on all client or server systems. Enterprise environments already managing and using .vhd files for virtual machine deployment will get the most benefit from the native-boot VHD capabilities. Using the .vhd file as a common image container format for virtual machines and designated hardware simplifies image management and deployment in an enterprise environment.

For more information about virtualization in Windows, see [this Microsoft Web site](http://go.microsoft.com/fwlink/?LinkId=142055). For more information about how to use VHDs with native boot, see [this Microsoft Web site](http://go.microsoft.com/fwlink/?LinkId=142054).

## <span id="BKMK_commonScenarios"></span><span id="bkmk_commonscenarios"></span><span id="BKMK_COMMONSCENARIOS"></span>Common Scenarios

-   Using disk-management tools to create and *attach* a VHD for offline image management. You can attach a VHD by using the **Attach vdisk** command which activates the VHD so that it appears on the host as a disk drive instead of as a .vhd file.

-   Mounting reference VHD images on remote shares for image servicing.

-   Maintaining and deploying a common reference VHD image to execute in either virtual or physical computers.

-   Configuring VHD files for native boot without requiring a full parent installation.

-   Configuring a computer to boot multiple local VHD files that contain different application workloads, without requiring separate disk partitions.

-   Using Windows Deployment Services (WDS) for network deployment of VHD images to target computers for native boot.

-   Managing desktop image deployment.


## <span id="BKMK_requirements"></span><span id="bkmk_requirements"></span><span id="BKMK_REQUIREMENTS"></span>Requirements

-   The local disk must have at least two partitions: a system partition that contains the Windows boot-environment files and Boot Configuration Data (BCD) store, and a partition to store the VHD file. The .vhd file format is supported for native boot on a computer with a Windows 7 boot environment, but you will have to update the system partition to a Windows 8 environment to use the .vhdx file format. For more information about how to add a Windows 8 or Windows 10 boot environment for native VHD boot, see [Boot to VHD (Native Boot): Add a Virtual Hard Disk to the Boot Menu](boot-to-vhd--native-boot--add-a-virtual-hard-disk-to-the-boot-menu.md).

-   The local disk partition that contains the VHD file must have enough free disk space for expanding a dynamic VHD to its maximum size and for the page file created when booting the VHD. The page file is created outside the VHD file, unlike with a virtual machine where the page file is contained inside the VHD.

## <span id="BKMK_benefits"></span><span id="bkmk_benefits"></span><span id="BKMK_BENEFITS"></span>Benefits

-   Using the same image-management tools for creating, deploying, and maintaining system images to be installed on designated hardware or on a virtual machine.

-   Deploying an image on a virtual machine or a designated computer, depending on capacity planning and availability.

-   Deploying Windows for multiple boot scenarios without requiring separate disk partitions.

-   Deploying supported Windows images in a VHD container file for faster deployment of reusable development and testing environments.

-   Replacing VHD images for server redeployment or recovery.

## <span id="BKMK_limitations"></span><span id="bkmk_limitations"></span><span id="BKMK_LIMITATIONS"></span>Limitations

-   Native VHD disk management support can attach approximately 512 VHD files concurrently.

-   Native VHD boot does not support hibernation of the system, although sleep mode is supported.

-   VHD files cannot be nested.

-   Native VHD boot is not supported over Server Message Block (SMB) shares.

-   Windows BitLocker Drive Encryption cannot be used to encrypt the host volume that contains VHD files that are used for native VHD boot, and BitLocker cannot be used on volumes that are contained inside a VHD.

-   The parent partition of a VHD file cannot be part of a volume snapshot.

-   An attached VHD cannot be configured as a *dynamic disk*. A dynamic disk provides features that basic disks do not, such as the ability to create volumes that span multiple disks (spanned and striped volumes), and the ability to create fault-tolerant volumes (mirrored and RAID-5 volumes). All volumes on dynamic disks are known as dynamic volumes.

-   The parent volume of the VHD cannot be configured as a dynamic disk.

## <span id="BKMK_typesOfVHDs"></span><span id="bkmk_typesofvhds"></span><span id="BKMK_TYPESOFVHDS"></span>Types of Virtual Hard Disks


Three types of VHD files can be created by using the disk-management tools:

-   **Fixed size.** A fixed size VHD is a file that is allocated to the size of the virtual disk. For example, if you create a virtual hard disk that is 2 gigabytes (GB) in size, the system will create a host file approximately 2 GB in size. Fixed hard-disk images are recommended for production servers and working with customer data. Recommended for production servers, to increase performance and help protect user data


-   **Dynamically expanding.** A dynamically expanding VHD is a file that is as large as the actual data written to it at any given time. As more data is written, the file dynamically increases in size. For example, the size of a file backing a virtual 2 GB hard disk is initially around 2 megabytes (MB) on the host file system. As data is written to this image, it grows with a maximum size of 2 GB.

    Dynamically expanding VHD are recommended only for development and testing environments. Dynamically expanding VHDs are recommended for development and testing only, because they can be corrupted more easily due to a catastrophic system shutdown, such as a power outage.

-   **Differencing.** A differencing hard disk image describes a modification of a parent image. This type of hard-disk image is not independent; it depends on another hard-disk image to be fully functional. The parent hard disk image can be any of the mentioned hard-disk image types, including another differencing hard-disk image.

    Differencing hard disk images are recommended only for development and testing environments.

## <span id="related_topics"></span>Related topics


[Deploy Windows on a VHD (Native Boot)](deploy-windows-on-a-vhd--native-boot.md)

[Boot to VHD (Native Boot): Add a Virtual Hard Disk to the Boot Menu](boot-to-vhd--native-boot--add-a-virtual-hard-disk-to-the-boot-menu.md)

[Download and install Windows PE (WinPE) so you can boot from a USB flash drive or an external USB hard drive](download-and-install-windows-pe--winpe--so-you-can-boot-from-a-usb-flash-drive-or-an-external-usb-hard-drive.md)

 

 






