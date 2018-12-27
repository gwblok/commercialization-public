---

Description: 'Windows 10 S WinPE, CI policy, OOBE, and DISM information.'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Windows 10 S manufacturing environment'

ms.date: 4/25/2018
ms.topic: article


---

# Manufacturing environment

## Overview

This topic covers the differences in the Windows 10 in S mode and Windows 10 S manufacturing environments from other Windows manufacturing environments.

## Code integrity policy

The code integrity policy (CI) blocks the execution of unsigned or improperly signed binaries. Using unsupported binaries is only recommended when performing lab or factory image customization, or during deployment where the execution environment is either WinPE or Audit Mode.

Once the CI policy is enabled on a system, it is enabled in two places:
1. Windows 10 in S mode, enforced at boot.
2. EFI firmware policy, enforced during firmware load and OS boot.

## WinPE

The Windows Preinstallation Environment (WinPE) behaves the same for Windows 10 in S mode and Windows 10 S as it does for Windows Home or Windows Professional.


For more information about WinPE, see [Windows PE](winpe-intro.md).

## DISM

### Adding a Windows 10 S image to a WIM

If you want a single WIM that includes multiple Windows editions including Windows 10 S, you can add/append your Windows 10 S image to an existing WIM, which allows you to specify the Windows 10 S image index during DISM /apply.

To see more about adding/appending images to an existing WIM, see [Append, apply, and export volume images with a Windows Image (.wim) file](append-a-volume-image-to-an-existing-image-using-dism--s14.md).

### Detect Windows 10 S with DISM

You can use DISM to detect Windows 10 S (offline in WinPE or in Audit mode). In Audit mode, use `DISM /online /get-currentedition`. If an image is Windows 10 S, the command should return S. In WinPE, use `DISM /image:c:\ /get-currentedition`.

See [DISM Windows edition-servicing command-line options](dism-windows-edition-servicing-command-line-options.md) to see additional commands for working with Windows editions.

## Audit mode

Audit mode is availabe when manufacturing a Windows 10 S PC. By default, the [blocked inbox components](windows-10-s-planning.md#what-is-blocked-in-windows-10-in-s-mode) are blocked in audit mode. If you need to use blocked inbox components during the manufacturing process, you can [enable manufacturing mode](windows-10-s-manufacturing-mode.md#enable-manufacturing-mode-1). If you enable manufacturing mode, you'll have to make sure to [disable manufacturing mode](windows-10-s-manufacturing-mode.md#remove-the-manufacturing-registry-key) prior to shipping your PC.

To learn more about Audit Mode, see [Audit Mode overview](audit-mode-overview.md).


## Factory device diagnostics

During factory testing, Win32-based diagnostic tools can be run by using one of the following options:

1. Windows 10 S in Audit Mode with the manufacturing registry key in place. If you’ve previously booted the PC without the manufacturing registry key in place, you’ll have to turn off Secure Boot before you can use Win32-based diagnostic tools.

    or 

2. In a separate non-Windows 10 S test operating system.

