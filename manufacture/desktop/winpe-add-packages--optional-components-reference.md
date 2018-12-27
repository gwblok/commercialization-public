---

Description: 'WinPE: Add packages (Optional Components Reference)'
ms.assetid: 67aa9c25-9fab-4970-8aa5-65f904969e8e
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'WinPE: Add packages (Optional Components Reference)'

ms.date: 05/02/2018
ms.topic: article
ms.custom: RS5
---

# WinPE Optional Components (OC) Reference

Add feature packages, also known as optional components, to Windows PE (WinPE).

## Where to get WinPE Optional Components

WinPE optional components become available when you install the **Windows Preinstallation Environment** with [the Windows Assessment and Deployment Kit](https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install) (ADK). Starting with Windows 10, version 1809, WinPE is an addon to the ADK that [you download](https://go.microsoft.com/fwlink/?linkid=2022233) and install after you install the ADK. 

Optional components are available in 32- and 64-bit architectures. The OCs you add to your WinPE image must be from the same ADK build and have the same architecture as your WinPE image. You can find WinPE optional components in the following locations after you install the ADK:

- **64-bit** `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE\_OCs\`
- **32-bit** `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\x86\WinPE\_OCs\`

## <span id="bkmk_1"></span><span id="BKMK_1"></span>How to add Optional Components

WinPE OCs are .cab packages that can be added to an offline Windows image. 

> [!Important]
> Some optional components have prerequisites that must be installed in order. The [table below](#span-idbkmkbspanspan-idbkmkbspanwinpe-optional-components-reference) includes information about prerequisites.

Before adding OCs to a WinPE image, you need a WinPE image (boot.wim). See [WinPE: Create bootable media](winpe-create-usb-bootable-drive.md) to learn how to make a set of WinPE working files that include a WinPE image. You'll find boot.wim at `sources\boot.wim` in your working files. 

Once you have a WinPE image to work with, you can add packages to it with `DISM /add-package`.  To learn more about using DISM to add packages to a Windows image, see [Add or remove packages offline using DISM](add-or-remove-packages-offline-using-dism.md).

Many WinPE optional components come split into two parts, a language-neutral package, and a set of language-specific packages. When installing an OC that has language-specific packages, you need to first add the language-neutral OC, and then add at least one of its associated language-specific packages. The language-specific and language-neutral resources must be of the same version. You can find OCs in the following folders:

- **Language-neutral** - `...\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\`
- **Language-specific** - `...\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\xx-xx\`


## WinPE Optional Components

> [!div class="op_single_selector"]
> - [WinPE-DismCmdlets](#18)
> - [WinPE-Dot3Svc](#11)
> - [WinPE-EnhancedStorage](#31)
> - [WinPE-FMAPI](#2)
> - [WinPE-Fonts-Legacy](#3)
> - [WinPE-Font Support-JA-JP](#4)
> - [WinPE-Font Support-KO-KR](#5)
> - [WinPE-Font Support-ZH-CN](#6)
> - [WinPE-Font Support-ZH-HK](#7)
> - [WinPE-GamingPeripherals](#9)
> - [WinPE-HTA](#8)
> - [Winpe-LegacySetup](#26)
> - [WinPE-MDAC](#1)
> - [WinPE-NetFX ](#10)
> - [WinPE-PlatformID](#16)
> - [WinPE-PowerShell](#17)
> - [WinPE-PPPoE](#12)
> - [WinPE-Rejuv](#21)
> - [WinPE-RNDIS](#13)
> - [WinPE-Scripting](#24)
> - [WinPE-SecureBootCmdlets](#19)
> - [WinPE-SecureStartup](#30)
> - [WinPE-Setup](#27)
> - [WinPE-Setup-Client](#28)
> - [WinPE-Setup-Server](#29)
> - [WinPE-SRT](#22)
> - [WinPE-StorageWMI ](#20)
> - [WinPE-WDS-Tools](#14)
> - [WinPE-WiFi-Package](#15)
> - [WinPE-WinReCfg ](#23)
> - [WinPE-WMI](#25)


| Area/Optional component name | Description |
|------------------------------|-------------|
| <span id="1"></span>Database/WinPE-MDAC | WinPE-MDAC supports Microsoft Open Database Connectivity (ODBC), OLE DB, and Microsoft ActiveX Data Objects (ADO). This set of technologies provides access to various data sources, such as Microsoft SQL Server. For example, this access enables queries to Microsoft SQL Server installations that contain ADO objects. You can build a dynamic answer file from unique system information. Similarly, you can build data-driven client or server applications that integrate information from a variety of data sources, both relational (SQL Server) and non-relational. |
| <span id="2"></span>File management/WinPE-FMAPI | WinPE-FMAPI provides access to the Windows PE File Management API (FMAPI) for discovering and restoring deleted files from unencrypted volumes. The FMAPI also provides the ability to use a password or recovery key file for the discovery and recovery of deleted files from Windows BitLocker Drive Encryption encrypted volumes. |
| <span id="3"></span>Fonts/WinPE-Fonts-Legacy | WinPE-Fonts-Legacy contains 32 font files for various languages/writing scripts. Some of these fonts are no longer used as UI fonts. For example, scripts such as Bangla, Devanagari, Gujarati, Gurmukhi, Kannada, Malayalam, Odia, Tamil, Telugu, and Sinhalese were covered by Mangal, Latha, Vrinda, Gautami, Kalinga, artika, Raavi, Shruti, and Tunga, but in Windows 8, they were all unified under Nirmala UI, a single, pan-Indian font. The following list shows the fonts and languages included in this optional component:<ul><li>estre.ttf Estrangelo Edessa (Syriac)</li><li>mvboli.ttf MV Boli (Thaana)</li><li>KhmerUI.ttf Khmer UI (Khmer UI)</li><li>KhmerUIB.ttf Khmer UI Bold (Khmer UI)</li><li>Laoui.ttf Lao UI (Lao)</li><li>Laouib.ttf Lao UI Bold (Lao)</li><li>daunpenh.ttf DaunPenh (Khmer)</li><li>moolbor.ttf MoolBoran (Khmer)</li><li>dokchamp.ttf DokChampa (Lao)</li><li>Himalaya.ttf Microsoft Himalaya (Tibetan)</li><li>monbaiti.ttf Mongolian Baiti (Mongolian)</li><li>MSYI.ttf Microsoft Yi Baiti (Yi Syllables)</li><li>nyala.ttf Nyala (Ethiopic)</li><li>sylfaen.ttf Sylfaen (Armenian & Georgian)</li><li>euphemia.ttf Euphemia (Unified Canadian Aboriginal Syllabics)</li><li>plantc.ttf Plantagenet Cherokee (Cherokee)</li></ul> |
| <span id="4"></span>Fonts/WinPE-Font Support-JA-JP | WinPE-Font Support-JA-JP contains two Japanese font families that are packaged as TrueType Collection (TTC) files. MS Gothic is the Windows Japanese user interface font in versions of Windows before Windows Vista. MS Gothic contains a large character set and embedded bitmaps to ensure legible rendering at small sizes. Meiryo, a font that was introduced in Windows Vista, is designed specifically for use in a Microsoft ClearType® rendering environment. Meiryo does not include embedded bitmaps. Instead, Meiryo relies on hinting instructions to produce legible characters at small sizes. In addition, the module contains two Japanese bitmap fonts, App932.fon and Vga932.fon. The module also contains a bitmap-only TrueType font, Jpn_font.ttf. This font is used on boot screens. |
| <span id="5"></span>Fonts/WinPE-Font Support-KO-KR| WinPE-Font Support-KO-KR contains three core Korean font families: Gulim, Batang and Malgun Gothic. Gulim is the legacy UI font and, as a TTC file, contains Gulim, GulimChe, Dotum and DotumChe. Batang is the legacy text font and is also a TTC file, containing Batang, BatangChe, GungSuh and GungSuhChe. Malgun Gothic, a font that was introduced in Windows Vista, is designed specifically for use in a ClearType rendering environment. Malgun Gothic does not include embedded bitmaps and instead relies on hinting instructions to produce legible characters at small sizes. |
| <span id="6"></span>Fonts/WinPE-Font Support-ZH-CN | WinPE-Font Support-ZH-CN contains two Chinese font families that are packaged as TTC files. Simsun is the Simplified Chinese user interface font in Windows versions before Windows Vista. Simsun contains embedded bitmaps to ensure legible rendering at small sizes. The other TTC font is MingLiu. MingLiu has embedded bitmaps and provides support for the Hong Kong Supplementary Character Set (HKSCS). YaHei, a font that was introduced in Windows Vista, is designed specifically for use in a ClearType rendering environment. YaHei does not include embedded bitmaps. YaHei relies on hinting instructions to produce legible characters at small sizes. In addition, the module contains one bitmap-only TrueType font, Chs_boot.ttf. This font is used on boot screens. |
| <span id="7"></span>Fonts/WinPE-Font Support-ZH-HK<p>and<p>WinPE-Font Support-ZH-TW | The Hong Kong and Taiwan optional components contain two Chinese font families that are packaged as TTC files. Simsun is the Simplified Chinese user interface font in Windows versions before Windows Vista. Simsun contains embedded bitmaps to ensure legible rendering at small sizes. MingLiu has embedded bitmaps and provides support for the HKSCS. JhengHei, a font that was introduced in Windows Vista, is designed specifically for use in a ClearType rendering environment. JhengHei does not include embedded bitmaps. JhengHei relies on hinting instructions to produce legible characters at small sizes. In addition, the module contains one bitmap-only TrueType font, Cht_boot.ttf. This font is used on boot screens. |
| <span id="8"></span>HTML/WinPE-HTA | WinPE-HTA provides HTML Application (HTA) support to create GUI applications through the Windows Internet Explorer script engine and HTML services. These applications are trusted and display only the menus, icons, toolbars, and title information that you create. |
| <span id="9"></span>Input/WinPE-GamingPeripherals | WinPE-GamingPeripherals adds support for Xbox wireless controllers in WinPE. |
| <span id="10"></span>Microsoft .NET/WinPE-NetFX | WinPE-NetFX contains a subset of the .NET Framework 4.5 that is designed for client applications.<p>Not all Windows binaries are present in Windows PE, and therefore not all Windows APIs are present or usable. Due to the limited API set, the following .NET Framework features have no or reduced functionality in Windows PE:<ul><li>Windows Presentation Foundation (WPF) (not supported)</li><li>Windows Runtime</li><li>.NET Framework Fusion APIs</li><li>Windows Control Library event logging</li><li>.NET Framework COM Interoperability</li><li>.NET Framework Cryptography Model</li></ul><p>**Dependencies:**<ul><li>Install **WinPE-WMI** before you install **WinPE-NetFX**.</li></ul>
| <span id="11"></span>Network/WinPE-Dot3Svc | Adds support for the IEEE 802.X authentication protocol on wired networks. For more info, see [WinPE Network Drivers: Initializing and adding drivers](winpe-network-drivers-initializing-and-adding-drivers.md). |
| <span id="12"></span>Network/WinPE-PPPoE | WinPE-PPPoE enables you to use Point-to-Point Protocol over Ethernet (PPPoE) to create, connect, disconnect, and delete PPPoE connections from Windows PE. PPPoE is a network protocol for encapsulating Point-to-Point Protocol (PPP) frames inside Ethernet frames. PPPoE enables Windows users to remotely connect their computers to the web. By using PPPoE, users can virtually dial from one computer to another over an Ethernet network, to establish a point-to-point connection between the computers. The computers can use this point-to-point connection to transport data packets. |
| <span id="13"></span>Network/WinPE-RNDIS | WinPE-RNDIS contains Remote Network Driver Interface Specification (Remote NDIS) support. WinPE-RNDIS enables network support for devices that implement the Remote NDIS specification over USB. Remote NDIS defines a bus-independent message set and a description of how this message set operates over various I/O buses. Therefore, hardware vendors do not have to write an NDIS miniport device driver. Because this Remote NDIS interface is standardized, one set of host drivers can support any number of bus-attached networking devices. |
| <span id="14"></span>Network/WinPE-WDS-Tools | WinPE-WDS-Tools includes APIs to enable the Image Capture tool and a multicast scenario that involves a custom Windows Deployment Services client. It must be installed if you intend to run the Windows Deployment Services client on a custom Windows PE image. |
| <span id="15"></span>Network/WinPE-WiFi-Package | WinPE-WiFi-Package is used by Windows Recovery Environment (Windows RE) for built-in recovery functions. This package is included in the base winre.wim file.<br><br> **Note:** Windows PE and Windows RE don't support general wireless networking functions. |
| <span id="16"></span>Windows PowerShell/WinPE-PlatformID | WinPE-PlatformID contains the Windows PowerShell cmdlets to retrieve the Platform Identifier of the physical machine. <br><br>**Dependencies:** Install **WinPE-WMI** and **WinPE-SecureStartup** before you install **WinPE-PlatformID**.<p>To use the Windows PowerShell cmdlet to retrieve the Platform Identifier, you will need install **WinPE-PowerShell** package. |
| <span id="17"></span>Windows PowerShell/WinPE-PowerShell | WinPE-PowerShell contains Windows PowerShell–based diagnostics that simplify using Windows Management Instrumentation (WMI) to query the hardware during manufacturing. You can create Windows PowerShell–based deployment and administrative Windows PE–based tools. In addition to deployment, you can use Windows PowerShell for recovery scenarios. Customers can boot in Windows RE and then use Windows PowerShell scripts to resolve issues. Customers are not limited to the toolsets that run in Windows PE. Similarly, you can build scripted offline solutions to recover some computers from no-boot scenarios.<br><br>WinPE-PowerShell has the following known limitations:<ul><li>Windows PowerShell remoting is not supported. Any cmdlets that have remoting functionality will return an error.</li><li>The Windows PowerShell Integrated Scripting Environment (ISE) is not supported.</li><li>Windows PowerShell 2.0 is not supported.</li></ul><p>**Dependencies**: Install **WinPE-WMI** > **WinPE-NetFX** > **WinPE-Scripting** before you install **WinPE-PowerShell**. |
| <span id="18"></span>Windows PowerShell/WinPE-DismCmdlets | WinPE-DismCmdlets contains the DISM PowerShell module, which includes cmdlets used for managing and servicing Windows images.<br><br>For more info, see [Deployment Imaging Servicing Management (DISM) Cmdlets in Windows PowerShell](use-dism-in-windows-powershell-s14.md).<p>**Dependencies**: Install **WinPE-WMI** > **WinPE-NetFX** > **WinPE-Scripting** > **WinPE-PowerShell** before you install **WinPE-DismCmdlets**. |
| <span id="19"></span>Windows PowerShell/WinPE-SecureBootCmdlets | WinPE-SecureBootCmdlets contains the PowerShell cmdlets for managing the UEFI (Unified Extensible Firmware Interface) environment variables for Secure Boot.<br><br>**Dependencies**: Install **WinPE-WMI** > **WinPE-NetFX** > **WinPE-Scripting** > **WinPE-PowerShell** before you install **WinPE-SecureBootCmdlets**. |
| <span id="20"></span>Windows PowerShell/WinPE-StorageWMI | WinPE-StorageWMI contains PowerShell cmdlets for storage management. These cmdlets use the Windows Storage Management API (SMAPI) to manage local storage, such as disk, partition, and volume objects. Or, these cmdlets use the Windows SMAPI together with array storage management by using a storage management provider. WinPE-StorageWMI also contains Internet SCSI (iSCSI) Initiator cmdlets for connecting a host computer or server to virtual disks on external iSCSI-based storage arrays through an Ethernet network adapter or iSCSI Host Bus Adapter (HBA).<br><br>**Dependencies**: Install **WinPE-WMI** > **WinPE-NetFX** > **WinPE-Scripting** > **WinPE-PowerShell** before you install **WinPE-StorageWMI**. |
| <span id="21"></span>Recovery/WinPE-Rejuv | WinPE-Rejuv is used by Windows Recovery Environment (Windows RE). This package is included in the base winre.wim file. |
| <span id="22"></span>Recovery/WinPE-SRT | WinPE-SRT is used by Windows RE. This package is included in the base winre.wim file. |
| <span id="23"></span>Recovery/WinPE-WinReCfg | WinPE-WinReCfg contains the Winrecfg.exe tool, and it enables the following scenarios:<p><ul><li>Boot from x86-based Windows PE to configure Windows RE settings on an offline x64-based operating system image.</li><li>Boot from x64-based Windows PE to configure Windows RE settings on an offline x86-based operating system image.</li></ul> |
| <span id="24"></span>Scripting/WinPE-Scripting | WinPE-Scripting contains a multiple-language scripting environment that is ideal for automating system administration tasks, such as batch file processing. Scripts that run in the Windows Script Host (WSH) environment can call WSH objects and other COM-based technologies that support Automation, such as WMI, to manage the Windows subsystems that are central to many system administration tasks.<br><br>**Dependencies**: Install WinPE-Scripting to make sure that full scripting functionality is available when you are using WinPE-NetFX and WinPE-HTA. The installation order is irrelevant. |
| <span id="25"></span>Scripting/WinPE-WMI | WinPE-WMI contains a subset of the Windows Management Instrumentation (WMI) providers that enable minimal system diagnostics. WMI is the infrastructure for management data and operations on Windows-based operating systems. You can write WMI scripts or applications to automate administrative tasks on remote computers. Additionally, WMI supplies management data to other parts of the operating system and products. |
| <span id="26"></span>Setup/Winpe-LegacySetup | Winpe-LegacySetup contains all Setup files from the \Sources folder on the Windows media. Add this optional component when you service Setup or the \Sources folder on the Windows media. You must add this optional component together with the optional component for the Setup feature. To add a new Boot.wim file to the media, add the parent WinPE-Setup, either of the children (WinPE-Setup-Client or WinPE-Setup-Server), and Media optional components. Media Setup is required to support Windows Server 2008 R2 installation. |
| <span id="27"></span>Setup/WinPE-Setup | WinPE-Setup is the parent of WinPE-Setup-Client and WinPE-Setup-Server. It contains all Setup files from the \Sources folder that are common to the client and the server. |
| <span id="28"></span>Setup/WinPE-Setup-Client | WinPE-Setup-Client contains the client branding files for the parent WinPE-Setup optional component.<br><br>**Dependencies**: Install **WinPE-Setup** before you install **WinPE-Setup-Client**. |
| <span id="29"></span>Setup/WinPE-Setup-Server | WinPE-Setup-Server includes the server branding files for the parent WinPE-Setup optional component.<br><br>**Dependencies**: Install **WinPE-Setup** before you install **WinPE-Setup-Server**. |
| <span id="30"></span>Startup/WinPE-SecureStartup | WinPE-SecureStartup enables provisioning and management of BitLocker and the Trusted Platform Module (TPM). It includes BitLocker command-line tools, BitLocker WMI management libraries, a TPM driver, TPM Base Services (TBS), the Win32_TPM class, the BitLocker Unlock Wizard, and BitLocker UI libraries. The TPM driver provides better support for both BitLocker and the TPM in this preboot environment.<br><br>**Dependencies**: Install **WinPE-WMI** before you install **WinPE-SecureStartup**. |
| <span id="31"></span>Storage/WinPE-EnhancedStorage | WinPE-EnhancedStorage enables Windows to discover additional functionality for storage devices, such as encrypted drives, and implementations that combine Trusted Computing Group (TCG) and IEEE 1667 ("Standard Protocol for Authentication in Host Attachments of Transient Storage Devices") specifications. This optional component enables Windows to manage these storage devices natively by using BitLocker. | 

 

## <span id="Windows_RE_optional_components"></span><span id="windows_re_optional_components"></span><span id="WINDOWS_RE_OPTIONAL_COMPONENTS"></span>Windows RE optional components


The default Windows RE image contains the following built-in optional components:
| Included Optional Component |
| ---- |
| WinPE-EnhancedStorage |
| WinPE-Rejuv |
| WinPE-Scripting |
| WinPE-SecureStartup |
| WinPE-Setup |
| WinPE-SRT |
| WinPE-WDS-Tools |
| WinPE-WMI |

## Add more languages to images that include optional components

Note: To add language packs using Windows PE, you may need to add pagefile support to Windows PE. For more information, see [Deployment Image Servicing and Management (DISM) Best Practices](deployment-image-servicing-and-management--dism--best-practices.md).

1.  On a mounted image, list the optional components in the Windows PE image:

    ```
    Dism /Get-Packages /Image:"C:\WinPE_amd64\mount"
    ```

2.  Review the resulting list of packages, and add the corresponding language packs for each package in the image, including the base Windows PE language pack.

    ```
    Dism /Add-Package /Image:"C:\WinPE_amd64\mount" /PackagePath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\lp.cab"

    Dism /Add-Package /Image:"C:\WinPE_amd64\mount" /PackagePath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\WinPE-HTA_fr-fr.cab"
    ```

    where … WinPE\_OCs\\fr-fr\\lp.cab represents the base Windows PE language pack.

3.  If you're adding language packs for Japan, Korea, or China, add the font packages for these languages. Here's an example for Japan:

    ```
    Dism /Add-Package /Image:"C:\WinPE_amd64\mount" /PackagePath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-Font Support-JA-JP.cab"
    ```

4.  Verify that the language packs are part of the image:

    ```
    Dism /Get-Packages /Image:"C:\WinPE_amd64\mount"
    ```

    Review the resulting list of packages and verify that the for each optional component, including the base Windows PE image, that there is an associated language pack.

5.  Change the regional settings to the language you'd like to use:

    ```
    Dism /Set-AllIntl:en-US /Image:"C:\WinPE_amd64\mount"
    ```

    To switch languages while in Windows PE, use `wpeutil setmuilanguage`.

## <span id="related_topics"></span>Related topics

[WinPE: Optimize and shrink the image](winpe-optimize.md)

[WinPE for Windows 10](winpe-intro.md)

[WinPE: Mount and Customize](winpe-mount-and-customize.md)

 

 






