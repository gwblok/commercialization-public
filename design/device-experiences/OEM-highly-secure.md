---
title: Standards for a highly secure Windows 10 device
description: This document provides guidance on the minimum standards for purchasing highly secure systems for Windows 10. 

ms.date: 10/25/2018
ms.topic: article


---
# Standards for a highly secure Windows 10 device
These standards are for general purpose laptops, tablets, 2-in-1’s, mobile workstations, and desktops. This topic applies specifically for **Windows 10 version 1809**. If you are a decision maker purchasing new devices and you want to enable the best possible security configuration, your device should meet or exceed these standards.

Beyond the hardware and firmware configurations outlined below, Microsoft recommends running [Windows 10 S](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-10s-security) for security. Windows 10 S is a specific configuration of Windows 10 Pro that offers a familiar Windows experience that’s streamlined for security and performance. Windows 10 S provides the best of the cloud and full featured apps, and is designed for modern devices. Windows Defender is always on and always up-to-date.

## Hardware

| Feature | Requirement | Details |
|---------|------------|----------|
| Processor generation | Systems must be on the latest, certified silicon chip for the current release of Windows | Intel 8th generation processors (Intel i3/i5/i7/i9-7x), Core M3-7xxx , Xeon E3-xxxx, and Xeon E5-xxxx processors, AMD 8th generation processors (A Series Ax-9xxx, E-Series Ex-9xxx, FX-9xxx) or ARM64 processors (Snapdragon SDM850)|
| Process architecture | Systems must have a processor that supports 64-bit instructions | Virtualization-based security (VBS) features require the Windows hypervisor, which is only supported on 64-bit IA processors, or ARM v8.2 CPUs |
| Virtualization | Systems must have a processor that supports Input-Output Memory Management Unit (IOMMU) device virtualization and all I/O devices must be protected by IOMMU/SMMU | Intel VT-d, AMD-Vi, or ARM64 SMMUs |
| Virtualization | Systems must also have virtual machine extensions with second level address translation (SLAT) | Intel Vt-x with Extended Page Tables (EPT), or AMD-v with Rapid Virtualization Indexing (RVI) |
| Virtualization | The presence of these hardware virtualization features must be unmasked and reported as supported by the system firmware, and these features must be available for the operating system to use ||
| Trusted Platform Module (TPM) | Systems must have a Trusted Platform Module (TPM), version 2.0, and meet the latest Microsoft requirements for the [Trusted Computing Group(TCG)](https://trustedcomputinggroup.org/) specification  | Intel (PTT), AMD, or discrete TPM from Infineon, STMicroelectronics, Nuvoton |
| Platform boot verification | Systems must implement cryptographically verified platform boot | Intel Boot Guard in Verified Boot mode, or AMD Hardware Verified Boot, or an OEM equivalent mode with similar functionality |
| RAM | Systems must have 8 gigabytes or more of system RAM |   |
| HARD DRIVE | Systems must have SSD/NVME as the optimal disk drive config for performance, experience and security  |   |

## Firmware

| Feature | Requirement | Details |
|---------|-------------|---------|
| Standard | Systems must have firmware that implements Unified Extension Firmware Interface (UEFI) version 2.5 or later | For more information, see [United Extensible Firmware Interface (UEFI) firmware requirements](OEM-UEFI.md) and [Unified Extensible Firmware Interface Forum specifications](http://uefi.org/specifications) |
| Class | Systems must have firmware that implements UEFI Class 2 or UEFI Class 3 | For more information, see [Unified Extensible Firmware Interface Forum specifications](http://uefi.org/specifications) |
| Code integrity | All drivers shipped inbox must be Hypervisor-based Code Integrity (HVCI) compliant | For more information, see the Enable virtualization-based isolation for Code Integrity section of [Driver compatibility with Device Guard in Windows 10](https://blogs.msdn.microsoft.com/windows_hardware_certification/2015/05/22/driver-compatibility-with-device-guard-in-windows-10/) |
| Secure boot | System's firmware must support UEFI Secure Boot and must have UEFI Secure Boot enabled by default | For more informaion, see [UEFI firmware requirements](OEM-UEFI.md) and [Secure Boot](OEM-secure-boot.md) |
| Secure MOR | System's firmware must implement Secure MOR revision 2 | For more information, see [Secure MOR implementation](https://docs.microsoft.com/en-us/windows-hardware/drivers/bringup/device-guard-requirements) |
| Update mechanism | Systems must support the Windows UEFI Firmware Capsule Update specification | For more information, see [Windows UEFI firmware update platform](https://docs.microsoft.com/en-us/windows-hardware/drivers/bringup/windows-uefi-firmware-update-platform) |
| Firmware support for SMM protection | System firmware must adhere to the recommendations for hardening SMM code described in the [Windows SMM Security Mitigations Table (WMST) specification](https://docs.microsoft.com/en-us/windows-hardware/drivers/bringup/acpi-system-description-tables). The WSMT specification contains details of an ACPI table that was created for use with Windows operating systems that support Windows virtualization-based security (VBS) features. Firmware must implement the protections described in the WSMT specification, and set the corresponding protection flags as described in the specification to report compliance with these requirements to the operating system.
| United Extensible Firmware Interface (UEFI) Memory Reporting | UEFI firmware must adhere to the following memory map reporting format and memory allocation guidelines in order for firmware to ensure compatibility with VBS. <ul><li>**UEFI v2.6 Memory Attributes Table (MAT)** - To ensure compatibility with VBS, firmware must cleanly separate EFI runtime memory ranges for code and data, and report this to the operating system. Proper segregation and reporting of EFI runtime memory ranges allows VBS to apply the necessary page protections to EFI runtime services code pages within the VBS secure region. Conveying this information to the OS is accomplished using the EFI_MEMORY_ATTRIBUTES_TABLE. To implement the UEFI MAT, follow these guidelines:<ol><li>The entire EFI runtime must be described by this table.</li> <li>All appropriate attribures for EfiRuntimeServicesData and EfiRuntimeServicesCode pages must be marked.</li> <li>These ranges must be aligned on page boundaries (4KB), and can not overlap.</li></ol><li>**EFI Page Protections** -All entries must include attributes EFI_MEMORY_RO, EFI_MEMORY_XP, or both. All UEFI memory that is marked executable must be read only. Memory marked writable must not be executable. Entries may not be left with neither of the attributes set, indicating memory that is both executable and writable.</li></ul>



