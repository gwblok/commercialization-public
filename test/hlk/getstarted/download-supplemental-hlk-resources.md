---
title: Download Supplemental HLK Resources
description: 


ms.date: 01/26/2018
ms.topic: article


---

# Download Supplemental HLK Resources

In addition to installing the Windows Hardware Lab Kit, you may also want to download and use playlists or filters. Certain tests also require downloading supplemental content.

## Windows Hardware Compatibility playlist

Get the official Windows Hardware Compatibility playlist so you can run the Windows HLK tests that ensure your hardware meets the requirements for compatibility with Windows 10. 
- [Download the Windows Hardware Compatibility playlist](http://aka.ms/HLKPlaylist)

Watch this video to learn more about playlists. 
> [!VIDEO https://assets.windowsphone.com/970594d5-fef1-4fc6-84ab-289a192cd107/WinHEC_HLK_Playlists_InvariantCulture_Default.mp4]

## Windows HLK filters 

When there is a problem in either a Windows HLK test or in the operating system itself that causes certification tests to fail incorrectly, we create an errata that allows partners to bypass the problematic test. Most errata use filters to automatically filter the failure from the submission results. Filters are applied within Windows HLK Studio. 

- [Download Windows HLK filters](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/windows-hardware-lab-kit-filters)

## Additional Windows HLK supplemental test content

Supplemental test content downloads are required for some tests related to graphics, media, and mean time between failures (MTBF). Download these files to complete Windows HLK testing in these areas. 

Required downloads for tests that use supplemental content: 

#### Media
- [HLK_DXVA.iso (Windows 10, version 1803)](https://go.microsoft.com/fwlink/?linkid=873023) 
- [HLK_DXVA.iso (Windows 10, version 1607, 1703, and 1709)](https://go.microsoft.com/fwlink/p/?LinkId=823112) 
- [HLK_HMFT.iso (Windows 10, version 1607, 1703, 1709, and 1803)](https://go.microsoft.com/fwlink/p/?LinkId=823113) 
- [HLK_PERF.iso (Windows 10, version 1607, 1703, 1709, and 1803)](https://go.microsoft.com/fwlink/p/?LinkId=823114) 

#### Graphics
- [HLK_GRFX_FOD.zip (Windows 10, version 1803)](https://go.microsoft.com/fwlink/p/?LinkId=873017)
- [HLK_GRFX_FOD.zip (Windows 10, version 1709)](https://go.microsoft.com/fwlink/p/?LinkId=859270) 
- [HLK_GRFX_FOD.zip (Windows 10, version 1703)](https://go.microsoft.com/fwlink/p/?linkid=845559) 
- [HLK_GRFX_FOD.zip (Windows 10, version 1607)](https://go.microsoft.com/fwlink/p/?linkid=842373)

#### Mobile
- [HLK_MOBILE.iso (Windows 10, version 1607, 1703, 1709)](https://go.microsoft.com/fwlink/p/?LinkId=823115) 

#### Private Cloud Simulator (PCS) 

This supplemental content package is required to pass the Device and Solutions PCS Tests. On the server that has the Windows HLK controller installed, place PCSFiles.vhd at the following location:

```C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\amd64```
- [Download PCSFiles.vhd (March 2017)](https://go.microsoft.com/fwlink/p/?LinkId=808763)


 

 


