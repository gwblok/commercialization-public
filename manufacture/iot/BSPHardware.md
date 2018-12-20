---
author: parameshbabu
Description: 'Learn how to use board supported packages in order to start assembling and manufacturing your device.'
title: 'BSP for Hardware'
ms.author: pabab
ms.date: 10/15/2018
ms.topic: article
ms.custom: RS5
---

# IoT Core Board Supported Packages (BSP)

Board Support Packages (BSP) is a collection of drivers/settings required to run IoT Core on a hardware platform. These are provided by the hardware vendors/silicon vendors.

There are two steps to creating your own BSP:

* First, find where you can get BSPs for supported platforms **below**.
* Second, learn how to create your own BSP by following the steps listed in the [IoT Manufacturing guide](https://docs.microsoft.com/windows-hardware/manufacture/iot/create-a-new-bsp).

## Raspberry Pi BSP

1. Download [RPi_BSP.zip](https://github.com/ms-iot/iot-adk-addonkit/releases/download/17134_v5.3/RPi_BSP.zip) to a local directory, say `C:\Downloads\RPi_BSP.zip`
2. Launch [IoTCorePShell](https://github.com/ms-iot/iot-adk-addonkit) and create or open a workspace using

    ``` powershell
    new-ws C:\MyWorkspace <oemname> arm
    (or) open-ws C:\MyWorkspace
    ```

3. Import the bsp using [Import-IoTBSP](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-IoTBSP.md) and build using

    ``` powershell
    Import-IoTBSP RPi2 C:\Downloads\RPi_BSP.zip
    (or) importbsp RPi2 C:\Downloads\RPi_BSP.zip
    buildpkg RPi2
    ```

> [!NOTE]
> Raspberry Pi BSP driver sources are available at [ms-iot/rpi-iotcore](https://github.com/ms-iot/rpi-iotcore)

## Intel BSPs

### BSP Links

| Chipset          | Download Link          |
|--------------- |--------------------- |
| Intel® Atom™ Processor E3800 Product Family and Intel® Celeron® Processor N2807/N2930/J1900  | [Download](https://downloadcenter.intel.com/download/25618) Intel® Embedded Drivers for Microsoft Windows® 10 IoT Core (32-bit and 64-bit) MR1 |
|Intel Atom® Processor E3900 Series, and Intel® Pentium® and Celeron® Processor N- and J-Series (Apollo Lake)| [Download](https://downloadcenter.intel.com/download/25618) Software Package: Intel Atom® E3900 SoC Family—Board Support Package (BSP) for Windows* 10 IoT Core 32-bit and 64-bit Platforms |
|Intel® Pentium® and Celeron® Processor N3000 Product Families, Intel® Atom™ x5-E8000 Processor, and Intel® Atom™ x5-Z8350 Processor| [Download](https://www.intel.com/content/www/us/en/embedded/products/braswell/software-and-drivers.html) Board Support Package for Intel Atom® Processor Windows* 10 IoT Core 32-bit and 64-bit Platforms |

### Instructions to use

Follow the steps below to use this BSP with the Windows 10 ADK release 1809 (17763) with iot-adk-addonkit version 6.0.

1. Download the BSP package and install
2. Launch IoTCorePShell, and create/open your workspace

    ``` powershell
    new-ws C:\MyWorkspace <oemname> arm
    (or) open-ws C:\MyWorkspace
    ```

3. Set the source location, either the installed directory or the zip file path

    ``` powershell
    $Source = "C:\Program Files (x86)\Intel IoT\Source-<arch>"
    (or)
    $Source = "C:\Downloads\IntelBSP.zip"
    ```

4. Import the bsp using [Import-IoTBSP](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-IoTBSP.md) and build using

    ``` powershell
    Import-IoTBSP <bspname> $Source
    (or) importbsp <bspname> $Source
    buildpkg <bspname>
    ```

## Qualcomm BSPs

### DragonBoard 410C

DragonBoard drivers are available at [DragonBoard 410C Software](https://developer.qualcomm.com/hardware/dragonboard-410c/software) under *Windows 10 IoT Core* section.

Steps to create the drivers :

1. Download the *_db410c_BSP.zip to a folder say, `C:\Downloads\*_db410c_BSP.zip`
2. Launch IoTCorePShell, and create/open your workspace

    ``` powershell
    new-ws C:\MyWorkspace <oemname> arm
    (or) open-ws C:\MyWorkspace
    ```

3. Import the bsp using [Import-QCBSP](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-QCBSP.md) and build using

    ``` powershell
    Import-QCBSP "C:\Downloads\*_db410c_BSP.zip" C:\prebuilt\DB410c_BSP -ImportBSP
    buildpkg QCDB410C
    ```

    Set `<BSPPkgDir>` setting in the IoTWorkspace.xml to `C:\prebuilt\DB410c_BSP`

## NXP BSPs

See [Window 10 IoT Core and NXP i.MX SoCs](https://docs.microsoft.com/windows/iot-core/learn-about-hardware/iotnxp) for information on the NXP BSP access and Ecosystem resources.

## Other helpful resources

* [Windows ADK IoT Core Add-Ons Overview](https://docs.microsoft.com/windows-hardware/manufacture/iot/iot-core-adk-addons)
* [IoT Core Add-Ons Powershell Commands](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/iot/iot-core-adk-addons-command-line-options)
* [IoT Core feature list](https://docs.microsoft.com/windows-hardware/manufacture/iot/iot-core-feature-list)
* [Channel9 Video on Manufacturing Guide](https://channel9.msdn.com/events/Build/2017/B8085)
