---
title: Windows Hardware Lab Kit
description: This guide provides information about the tests that are included in the Windows Hardware Lab Kit, and instructions on how to build a test environment, automate driver and system testing, and create a submission package required to participate in the Windows Hardware Compatibility Program.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fed4ec97-81cb-487c-ac17-de7c6884892b


ms.date: 11/02/2018
ms.topic: article


---

# Windows Hardware Lab Kit

The Windows Hardware Lab Kit (Windows HLK) is a test framework used to test hardware devices for Windows 10. To qualify for the [Windows Hardware Compatibility Program](https://docs.microsoft.com/en-us/windows-hardware/design/compatibility/), your product must pass certain tests using the Windows HLK.

This guide provides information about the tests that are included in the Windows Hardware Lab Kit, and instructions on how to build a test environment, automate driver and system testing, and create a submission package required to participate in the [Windows Hardware Compatibility Program](https://docs.microsoft.com/en-us/windows-hardware/design/compatibility/).

If you’re developing for Windows 10, you need the latest Windows HLK. This kit helps you ensure that the drivers and the system you develop are certified as compatible with Windows 10. 

>[!NOTE]
>New for 1809: Certify using the Virtual HLK (VHLK)! The VHLK is the entire Hardware Lab Kit pre-installed and pre-configured on a VHDX, ready to boot as a virtual machine. Use the VHLK to save setup time, quickly stand up a controller, and run Windows Hardware Certification from a virtual machine. 


|To certify... | Download...|
|-----------------|------------| 
| Windows 10, version 1809    |  [Windows HLK, version 1809](https://go.microsoft.com/fwlink/?linkid=2026646) or <br> [Windows Virtual HLK (VHLK), version 1809](https://www.microsoft.com/en-us/evalcenter/evaluate-virtual-hardware-lab-kit) - NEW!|
| Windows 10, version 1803    |  [Windows HLK, version 1803](https://go.microsoft.com/fwlink/p/?LinkId=873010) |
| Windows 10, version 1709    |  [Windows HLK, version 1709](https://go.microsoft.com/fwlink/p/?LinkId=859231) | 
| Windows 10, version 1703<br>Windows 10, version 1607| [Windows HLK, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=733613)| 
| Windows Server 2016 |[Windows HLK, version 1607](https://go.microsoft.com/fwlink/p/?LinkID=404112)|

>[!NOTE]
>Windows HLK only supports testing on Windows 10 and Windows Server 2016 systems. For testing previous versions of Windows, use the [Hardware Certification Kit](https://msdn.microsoft.com/en-us/library/windows/hardware/jj124227(v=vs.85).aspx) for Windows 8.1. 
 
## Windows Hardware Compatibility Program

To qualify for the Windows Hardware Compatibility Program, your product must pass certain tests using the Windows HLK.
For guidance on which kit to use for compatibility certification, see the [Windows Hardware Compatibility Program](https://docs.microsoft.com/en-us/windows-hardware/design/compatibility/) and the [Windows Hardware Certification Blog](https://blogs.msdn.microsoft.com/windows_hardware_certification/). 

>[!IMPORTANT]
> Certification for Windows Server 2016, Azure Stack, and SDDC must continue to meet the Windows Hardware Compatibility Requirements as stated in version 1607 of documentation; must use version 1607 of the HLK (build 14393) with matching playlist and supplemental content to generate logs; and must follow policies as stated in the Windows Server Policy document. Questions about the Azure Stack, SDDC programs, or how to submit the results for solution validation should be directed to the appropriate Microsoft technical account manager or partner management contact. 

## Download Windows Hardware Compatibility playlist

Get the official Windows Hardware Compatibility playlist so you can run the Windows HLK tests that ensure your hardware meets the requirements for compatibility with Windows 10. 
- [Download the Windows Hardware Compatibility playlist](http://aka.ms/HLKPlaylist)

Watch the WinHEC video on [HLK Playlists](https://assets.windowsphone.com/970594d5-fef1-4fc6-84ab-289a192cd107/WinHEC_HLK_Playlists_InvariantCulture_Default.mp4) to learn more.

## Download Windows HLK Filters 

When there is a problem in either a Windows HLK test or in the operating system itself that causes certification tests to fail incorrectly, we create an errata that allows partners to bypass the problematic test. Most errata use filters to automatically filter the failure from the submission results. Filters are applied within Windows HLK Studio. 

- [Download Windows HLK filters](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/windows-hardware-lab-kit-filters)

## Download Windows HLK Supplemental Test Content

### Supplemental Content for Media, Graphics, Mean Time Between Failures (MTBF), and Private Cloud Simulator Tests

Supplemental test content downloads are required for some tests related to graphics, media, and mean time between failures (MTBF). Download these files to complete Windows HLK testing in these areas. 

Required downloads for tests that use supplemental content: 

#### Media
- [HLK_DXVA.iso (Windows 10, version 1809)](https://go.microsoft.com/fwlink/?linkid=2027245&clcid=0x409)
- [HLK_DXVA.iso (Windows 10, version 1803)](https://go.microsoft.com/fwlink/?linkid=873023) 
- [HLK_DXVA.iso (Windows 10, version 1607, 1703, and 1709)](https://go.microsoft.com/fwlink/p/?LinkId=823112) 
- [HLK_HMFT.iso (Windows 10, version 1809)](https://go.microsoft.com/fwlink/?linkid=2027116&clcid=0x409) 
- [HLK_HMFT.iso (Windows 10, version 1607, 1703, 1709, and 1803)](https://go.microsoft.com/fwlink/p/?LinkId=823113) 
- [HLK_PERF.iso (Windows 10, version 1607, 1703, 1709, 1803, and 1809)](https://go.microsoft.com/fwlink/p/?LinkId=823114) 

#### Graphics
- [HLK_GRFX_FOD.zip (Windows 10, version 1809)](https://go.microsoft.com/fwlink/?linkid=2027144&clcid=0x409)
- [HLK_GRFX_FOD.zip (Windows 10, version 1803)](https://go.microsoft.com/fwlink/p/?LinkId=873017)
- [HLK_GRFX_FOD.zip (Windows 10, version 1709)](https://go.microsoft.com/fwlink/p/?LinkId=859270) 
- [HLK_GRFX_FOD.zip (Windows 10, version 1703)](https://go.microsoft.com/fwlink/p/?linkid=845559) 
- [HLK_GRFX_FOD.zip (Windows 10, version 1607)](https://go.microsoft.com/fwlink/p/?linkid=842373)

#### Mobile
- [HLK_MOBILE.iso (Windows 10, version 1607, 1703, 1709)](https://go.microsoft.com/fwlink/p/?LinkId=823115) 

#### Private Cloud Simulator (PCS) 

This supplemental content package is required to pass the Device and Solutions PCS Tests. On the server that has the Windows HLK controller installed, place PCSFiles.vhd at the following location:

```C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\amd64```

|To certify...           | Download...    | SHA256 |
|------------------------|----------------|--------------------|
| Windows Server 2016    |  [PCSFiles.vhd](http://download.microsoft.com/download/5/9/F/59FF2124-30FA-4BFA-9BE5-5D55E736E6A0/PcsFiles.vhd) | 8AE4F86D0F40B4304CA4DC8CBCFA989885E3507FCB0FFDBF969DDF10542F0035 |

You can use Get-FileHash PowerShell cmdlet to compute the hash value for a file.

## Download HLK Offline Documentation

This documentation is also available in .chm format for offline use.

- [Download HLK offline documentation](http://download.microsoft.com/download/F/7/6/F76FF298-B35C-44F0-912D-9AD132E7794E/HLK.chm)

