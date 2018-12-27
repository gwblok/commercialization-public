---

Description: 'Recovery and push button reset in Windows 10 S.'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Recovery in Windows 10 S'

ms.date: 07/07/2017
ms.topic: article


---

# Recovery in Windows 10 S

## Built-in recovery

Windows 10 S includes a recovery solution that enables a user to restore, refresh, or troubleshoot their PC. Recovery in Windows 10 S has some differences from other editions of Windows. These differences are:

- Third party recovery solutions are NOT supported
- Extensibility points for customizations documented in this section is supported
    - OEM tools in WinRE is not supported
    - CMD prompt in WinRE will be enabled but only allow execution of inbox WinRE binaries
    - Extensibility script must be in the form of a *.CMD
    - Does not call any of the blocked inbox components except reg.exe and wmic.exe

## Validating recovery in your deployment

After you configure your Windows 10 S PC for recovery scenarios, validate that it is working properly by verifying that these scenarios run successfully:

- Run refresh recovery and validate the user files are preserved and your factory desktop customizations are restored.
- Run reset recovery and validate the user files and profile are removed and your factory desktop customizations are restored.
- Validate extensibility scripts in the simulated RS3 enforcement level using the provided policy file.
- If you created a recovery package with ScanState, ensure that the manufacturing key was excluded from capture.