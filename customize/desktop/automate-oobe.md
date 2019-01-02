---
title: Automate OOBE
description: Use Unattend to prevent some or all of the user interface (UI) pages from appearing in Windows Out of Box Experience (OOBE).
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 04/24/2018
ms.topic: article
ms.custom: RS5
---
# Automate OOBE

You can use Unattend settings to prevent some or all of the user interface (UI) pages from appearing in Windows OOBE.

To learn more about creating an answer file using Unattend, as well as a full list of Unattend settings available to you, see the [Unattended Windows Setup Reference](unattend/index.md).

| Setting                                           | Configuration pass           | Description                        | Applies to                        |
|:--------------------------------------------------|:-----------------------------|:-----------------------------------|:----------------------------------|
| Microsoft-Windows-International-Core settings: [InputLocale](unattend/microsoft-windows-international-core-inputlocale.md), [SystemLocale](unattend/microsoft-windows-international-core-systemlocale.md), [UILanguage](unattend/microsoft-windows-international-core-uilanguage.md), and [UserLocale](unattend/microsoft-windows-international-core-userlocale.md).              | oobeSystem    | Specifies the region-specific defaults of the Windows installation.   | Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) and Windows Server 2016  |
| [Microsoft-Windows-Shell-Setup/UserAccounts](unattend/microsoft-windows-shell-setup-useraccounts.md)   | oobeSystem            |  Specifies the user accounts, and passwords, to create on the Windows installation. The account can be a user account, a domain account, or the default administrator account.    | Windows 10 for desktop editions and Windows Server 2016 |
| Microsoft-Windows-Shell-Setup/OOBE settings: [HideEULAPage](unattend/microsoft-windows-shell-setup-oobe-hideeulapage.md), [HideOEMRegistrationScreen](unattend/microsoft-windows-shell-setup-oobe-hideoemregistrationscreen.md), [HideOnlineAccountScreens](unattend/microsoft-windows-shell-setup-oobe-hideonlineaccountscreens.md), [HideWirelessSetupInOOBE](unattend/microsoft-windows-shell-setup-oobe-hidewirelesssetupinoobe.md), and [HideLocalAccountScreen](unattend/microsoft-windows-shell-setup-oobe-hidelocalaccountscreen.md).    | oobeSystem        | Specifies whether certain OOBE screens will be hidden.  | Windows 10 for desktop editions and Windows Server 2016 |
| [Microsoft-Windows-Shell-Setup/OOBE/ProtectYourPC](unattend/microsoft-windows-shell-setup-oobe-protectyourpc.md) | oobeSystem        | Specifies whether your device is configured with Express settings, such as sending data to Microsoft, letting Windows and apps request the user's localization, and turning on protection against malicious web content. | Windows 10 for desktop editions and Windows Server 2016  |

## Related topics

[Automate Windows Setup](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/automate-windows-setup)

[Windows Auto Pilot](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/windows-10-autopilot)
