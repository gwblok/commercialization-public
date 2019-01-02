---
title: DXVA Testing Prerequisites
description: DXVA Testing Prerequisites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b4a88365-9960-4f12-a70f-27c63d946b86
author: alsepkow
ms.author: alsepkow
ms.date: 10/11/2018
ms.topic: article
---

# DXVA Testing Prerequisites

 
## <span id="BKMK_HCK_HMFT_hR"></span><span id="bkmk-hck-dxva-codecpacks"></span><span id="BKMK_HCK_DXVA_CODECPACKS"></span>Supplemental Codec Packs


Starting with RS5 (Redstone 5) the HLK controller is now capable of deploying and installing codec packs. If your test machines include hardware which reports support for codecs that require a codec pack to be installed and your test machine images **do not** include these codec packs then you must place the codec packs on your controller.
As of fall 2018 there are two codec packs that you may require (HEVC and MPEG2).

**You can find the codec packs in the OEM inbox apps iso. (Available through EEAP)**

The HLK controller is preprovisioned to contain placeholder appx packages at:

 -   C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\CodecPacks\amd64\
 -   C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\CodecPacks\arm\
 -   C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\CodecPacks\arm64\
 -   C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\CodecPacks\x86\

**How to add codec packs on your HLK controller:**
1. Simply replace the appx in the directory for the architecture of your system under test.
2. Run your tests. Your controller will automatically install the codec pack on systems under test.

For example, if you are only testing x64 systems and need to run the HEVC tests. Then simply replace the following placeholder appx with the appx package from the OEM inbox apps iso.

C:\Program Files (x86)\Windows Kits\10\Hardware Lab Kit\Tests\CodecPacks\amd64\Microsoft.HEVCVideoExtension_8wekyb3d8bbwe.x64.appx

## <span id="BKMK_HCK_HMFT_hR"></span><span id="bkmk-hck-dxva-internet"></span><span id="BKMK_HCK_DXVA_internet"></span>Internet Connection


Certain tests now **require** internet access. Specifcally:

 -   DRM Tests - An internet connection is required for license acquisition.
 -   Tests with supplemental codec packs - An internet connection is required for codec pack validation.