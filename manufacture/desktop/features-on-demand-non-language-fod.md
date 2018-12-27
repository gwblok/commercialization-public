---

Description: 'Features on Demand (capabilities), introduced in Windows 10, are Windows feature packages that can be added at any time. This page describes non-language FODs.'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Available features on demand'

ms.date: 11/26/2018
ms.topic: article
ms.custom: RS5
---

# Available Features on Demand

The following Features on Demand are available for Windows 10 and Windows Server. Some FODs come preinstalled with Windows and are all you need to ship a Windows device. You can, however, add additional FODs to support additional hardware features or enable certain use cases.

You can use either `DISM /image:<path_to_image> /get-capabilities` or `DISM /online /get-capabilities` to see which Features on Demand are available in your image of Windows 10. To see how to add Features on Demand, see [Features on Demand](features-on-demand-v2--capabilities.md). 

To see available Features on Demand for languages and regions, see [Language and region Features on Demand](features-on-demand-language-fod.md)

## Preinstalled FODs

The following Features on Demand come preinstalled in a Windows image. Don't remove these FODs from the Windows image:

### Internet Explorer

Internet Explorer Features on Demand enable preinstallation of Internet Explorer. Internet Explorer will not be enabled on a device that doesn't include this Feature on Demand.

**Feature**: Internet Explorer 11
- **Capability name**: Browser.InternetExplorer~~~~0.0.11.0
- **CAB name**: Microsoft-Windows-InternetExplorer-Optional-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 1.66 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1703 and later

### Math Recognizer

This feature on demand adds the Math Input Panel, Control and Recognizer.

**Feature**: Math Recognizer 
- **Capability name**: MathRecognizer~~~~0.0.1.0
- **CAB name**: Microsoft-Windows-TabletPCMath-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 17.46 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1809 and later

### OneSync

This Feature on Demand is a mail, contacts, and calendar sync component. Not including this Feature on Demand on your Windows image will cause UWP apps such as Mail, People, and Calendar to not be able to properly sync.

**Feature**: Exchange ActiveSync and Internet Mail Sync Engine 
- **Capability name**: OneCoreUAP.OneSync~~~~0.0.1.0 
- **CAB name:**: Microsoft-OneCore-ApplicationModel-Sync-Desktop-FOD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 12.83 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1709 and later

### OpenSSH client

The OpenSSH client Feature on Demand enables the use of OpenSSH on a Windows PC.

**Feature**: OpenSSH Client
- **Capability name**: OpenSSH.Client~~~~0.0.1.0 
- **CAB name**: OpenSSH-Client-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 5.28 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1709 and later

### Quick Assist

Microsoft Quick Assist allows users to share their screen with Microsoft support agents or other trusted people. This FOD is preinstalled, but not available on the FOD ISO.

**Feature**: Microsoft Quick Assist 
- **Capability name**: App.Support.QuickAssist~~~~0.0.1.0
- **CAB name**: 
- **Install size**: 1.51 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1607 and later

## FODs that are not preinstalled, but may need to be preinstalled

The following FODs are not preinstalled in a Windows image, but we recommend preinstalling them to enable certain scenarios.

### <span id="DOTNET"></span><span id="dotnet"></span> .NET Framework  

.NET framework adds support for 3rd party .NET3.x apps. If this Feature on Demand is not installed, .NET3.x apps won't work.

**Recommendation:** Preinstall these Features on Demand on devices that are preloaded with apps that require .NET3.x.

**Feature**: NetFx3
- **Capability name**: NetFX3~~~~
- **CAB name**: Microsoft-Windows-NetFx3-OnDemand-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 301 MB
- **Satellites**: None
- All versions of Windows 10

### Mixed Reality

This Feature on Demand enables Mixed Reality (MR) devices to be used on a PC. If this Feature on Demand is not present, MR devices may not function properly.

**Note:** Make sure to add this feature on demand prior to adding an update.

**Recommendation:** Recommended for MR-Ready badged PCs, otherwise do not preinstall. 

> [!NOTE]
> The Mixed Reality Feature on Demand has a large installation size. This FOD also requires the installation of an additional data assets package, if an updated asset package is available. Updates to the Mixed Reality FOD are available via regular Windows LCUs. The data assets update package, when available, is a separate download from the [Microsoft Update Catalog](http://www.catalog.update.microsoft.com). 

**Feature**: Windows Mixed Reality 
- **Capability name**: Analog.Holographic.Desktop~~~~0.0.1.0 
- **CAB name**: Microsoft-Windows-Holographic-Desktop-FOD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 1.93 GB 
- **Satellites**: None
- **Availability**: Windows 10, version 1703 and later

### Retail Demo Experience (RDX)

These Features on Demand add the retail demo package to a device, for use in retail stores. These features are available as .cab packages on the FOD ISO, and should be added with `DISM /add-package`. See [Add or remove packages offline with DISM](add-or-remove-packages-offline-using-dism.md).

**Recommendation:** Preinstall on devices that will be shipped to a retail store. Install the language-neutral FOD, as well as at least one language-specific FOD to ensure that any Windows 10 device can be used as a demo device. Windows will automatically remove these FODs after a user goes through a non-RetailDemo OOBE. See [Retail demo experience](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/retail-demo-experience) for more information about configuring RDX.

**Feature**: Language-neutral Retail Demo Content 
- **CAB name**: Microsoft-Windows-RetailDemo-OfflineContent-Content-Package.cab 

**Feature**: Language-specific Retail Demo Content 
- **CAB name**: Microsoft-Windows-RetailDemo-OfflineContent-Content-*language-country*-Package.cab


### Server Core App Compatibility

[Server Core App Compatibility](https://docs.microsoft.com/en-us/windows-server/get-started-19/install-fod-19) significantly improves the app compatibility of the Windows Server Core installation option by including a subset of binaries and packages from Windows Server with Desktop Experience, without adding all components of the Windows Server Desktop Experience graphical environment. This FOD is available on the Server FOD ISO.

**Feature**: Server Core App Compatibility 
- **CAB name**: Microsoft-Windows-Server-AppCompat-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Availability**: Windows Server 2019 (Server Core only)


## FODs that are not preinstalled

The following is a list of additional FODs you can add to your Windows image to enable additional functionality based on your hardware configuration or to support additional use cases.


### Accessibility

This Feature on Demand enables Braille devices to work with the inbox Narrator screen reader. Without this Feature on Demand, Braille drivers and translation tables will be missing, causing Braille to not function properly.

**Recommendation:** Don't include these Features on Demand in your image, as doing so could conflict with Braille device rights restrictions.

This Feature on Demand's installation can be triggered by a user from the Windows Settings app. 

**Feature** Accessibility - Braille Support 
- **Capability name**: Accessibility.Braille~~~~0.0.1.0 
- **CAB name**: Microsoft-Windows-Accessibility-Braille-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 13.47 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1703 and later

### Developer Mode

An on-device diagnostic platform used via a browser.  Installs a SSH server on the device for UWP remote deployment as well as Windows Device Portal.

Enabling Developer Mode will attempt to auto-install this Feature on Demand. On devices that are WSUS-managed, this auto-install will likely fail due to WSUS blocking FOD packages by default. If this Feature on Demand is not successfully installed, device discovery and Device Portal can't be enabled, preventing remote deployment to the device.

**Recommendation:** In general, don't preinstall on devices. If you are building an image for "developer edition" devices, where the primary market for the device is developers or users who plan on developing or testing UWPs, consider preinstalling.

**Feature** Windows Developer Mode 
- **Capability name**: Tools.DeveloperMode.Core~~~~0.0.1.0
- **CAB name**: Microsoft-OneCore-DeveloperMode-Desktop-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 13.20 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1607 and later

### Graphics Tools

Used for Direct3D application development.  It is typically installed by AAA game engine developers, enterprise graphics software developers, or niche hobbyists.  

**Recommendation:** Don't install. This Feature on Demand is only needed by specific users who can trigger installation through Visual Studio when certain optional packages are chosen at install.

**Feature**: Graphics Tools 
- **Capability name**: Tools.Graphics.DirectX~~~~0.0.1.0
- **CAB name**: Microsoft-OneCore-Graphics-Tools-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 69.01 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1607 and later


### Microsoft WebDriver

This Feature on Demand enables automated testing of Microsoft Edge and WWA's or WebView controls. This was previously available as a [separate download](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/).

**Recommendation:** In general, don't preinstall on devices. If you are building an image for "developer edition" devices, where the primary market for the device is developers or users who plan on testing websites in Microsoft Edge or web content in UWPs, consider preinstalling.

**Feature**: Microsoft WebDriver 
- **Capabilityname**: Microsoft.WebDriver~~~~0.0.1.0 
- **CAB name**: Microsoft-WebDriver-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 909 KB
- **Satellites**: None
- **Availability**: Windows 10, version 1809 and later

### MSIX Packaging Tool Driver

MSIX Packaging tool driver monitors the environment to capture the changes that an application installer is making on the system to allow MSIX Packaging Tool to repackage the installer as MSIX package.

**Recommendation:** Don’t preinstall on devices.

**Feature**: MSIX Packaging Tool Driver 
- **Capability name**: Msix.PackagingTool.Driver~~~~0.0.1.0 
- **CAB name**: Msix-PackagingTool-Driver-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 37.74 KB
- **Satellites**: None
- **Availability**: Windows 10, version 1809 and later


### Networking tools 

The following tools are available as Features on Demand

**Recommendation:** Don’t preinstall on devices.

**Feature**: RAS Connection Manager Administration Kit (CMAK) 
- **Description**: Create profiles for connecting to remote servers and networks
- **Capability name**: RasCMAK.Client~\~~\~0.0.1.0  
- **CAB name**: Microsoft-Windows-RasCMAK-Client-Package\~31bf3856ad364e35\~amd64~en-US~.cab 
- **Satellites**: Yes
- **Install size**: 702.89 KB 
- **Availability**: Windows 10, version 1809 and later


**Feature**: RIP Listener
- **Description**: Listens for route updates sent by routers that use the Routing Information Protocol version 1 (RIPV1)
- **Capability name**: RIP.Listener~\~~\~0.0.1.0  
- **CAB name**: Microsoft-Windows-RasRip-Package\~31bf3856ad364e35\~amd64~en-US~.cab
- **Satellites**: Yes 
- **Install size**: 45.11 KB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Simple Network Management Protocol (SNMP) 
- **Description**: This feature includes SNMP agents that monitor the activity in network devices and report to the network console workstation
- **Capability name**: SNMP.Client~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-SNMP-Client-Package\~31bf3856ad364e35\~amd64~en-US~.cab
- **Satellites**: Yes 
- **Install size**: 1.11 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: SNMP WMI Provider 
- **Description**: Enables WMI clients to consume SNMP information through the CIM model as implemented by WMI
- **Dependencies**: SNMP.Client
- **Capability name**: WMI-SNMP-Provider.Client~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-WMI-SNMP-Provider-Client-Package\~31bf3856ad364e35\~amd64~en-US~.cab 
- **Satellites**: Yes	
- **Install size**: 1.58 MB 
- **Availability**: Windows 10, version 1809 and later


### OpenSSH Server

The OpenSSH server Feature on Demand enable the use of OpenSSH on a Windows PC.

**Recommendation:** Don't include this Feature on Demand on your image.

**Feature**: OpenSSH Server 
- **Capability name**: OpenSSH.Server~~~~0.0.1.0 
- **CAB name**: OpenSSH-Server-Package\~31bf3856ad364e35\\~amd64\~\~.cab
- **Install size**: 5.61 MB 
- **Satellites**: None
- **Availability**: Windows 10, version 1709 and later


### Printing

These Features on Demand are for devices running Windows Server as a Print Server role which supports Azure AD joined devices.  If this FOD is not installed, then a Windows Server acting as a Print Server will only support the printing needs of traditional domain joined devices.  Azure AD joined devices will not be able to discover corporate printers.

**Recommendation:** Only preinstall the Features on Demand on Windows Server devices running as a Print Server role.

**Feature**: Enterprise Cloud Print 
- **Capability name**: Print.EnterpriseCloudPrint~~~~0.0.1.0 
- **CAB name**: Microsoft-Windows-Printing-EnterpriseCloudPrint-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 3.28 MB 
- **Satellites**: None
- **Availability**: Windows 10, version 1709 and later

**Feature**: Mopria Cloud Service
- **Capability name**: Print.MopriaCloudService~~~~0.0.1.0 
- **CAB name**: Microsoft-Windows-Printing-MopriaCloudService-Package\~31bf3856ad364e35\~amd64~~.cab
- **Install size**: 11.13 MB 
- **Satellites**: None
- **Availability**: Windows 10, version 1709 and later

### Remote server administration tools (RSAT)

Remote Server Administration Tools for Windows 10 lets IT administrators manage Windows Server from a remote computer running the full release version of Windows 10. 

**Recommendation:** OEMs shouldn't preinstall these Features on Demand.

**Feature**: Active Directory Domain Services and Lightweight Directory Services Tools 
- **Description**: For remotely managing AD DS and AD LDS on Windows Server
- **Dependencies**: Rsat.ServerManager.Tools 
- **Capability name**: Rsat.ActiveDirectory.DS-LDS.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-ActiveDirectory-DS-LDS-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 17.01 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: BitLocker Drive Encryption Administration Utilities
- **Description**: Tools for managing BitLocker Drive Encryption Features
- **Dependencies**: Rsat.ActiveDirectory.DS-LDS.Tools 
- **Capability name**: Rsat.BitLocker.Recovery.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-BitLocker-Recovery-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 52.35 KB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Active Directory Certificate Services Tools 
- **Description**: Remotely manage AD CS on Windows Server
- **Capability name**: Rsat.CertificateServices.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-CertificateServices-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes 
- **Install size**: 5.35 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: DHCP Server Tools 
- **Description**: DHCP MMC snap-in, SHCP server netsh context, and Windows PowerShell module for DHCP Server
- **Capability name**: Rsat.DHCP.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-DHCP-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 7.09 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: DNS Server Tools 
- **Description**: DNS MMC snap-in, dnscmd.exe command-line tool, and Windows PowerShell module for DHCP Server
- **Capability name**: Rsat.Dns.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-DNS-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes 
- **Install size**: 6.15 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Failover Clustering Tools 
- **Description**: Failover Cluster Manager snap-in, the Cluster-Aware Updating interface, and the Failover Cluster module for Windows PowerShell
- **Dependencies**:  Rsat.FileServices.Tools 
- **Capability name**: Rsat.FailoverCluster.Management.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-FailoverCluster-Management-Tools-FOD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 34.35 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: File Services Tools
- **Description**: For remotely managing the File Services role on Windows Server 
- **Dependencies**: Rsat.ServerManager.Tools
- **Capability name**: Rsat.FileServices.Tools~\~\~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-FileServices-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes 
- **Install size**: 17.14 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Group Policy Management Tools 
- **Capability name**: Rsat.GroupPolicy.Management.Tools~\~~\~0.0.1.0  
- **Description**: Group Policy Management Console, GP Management Editor, and GP Started GPO Editor 
- **CAB name**: Microsoft-Windows-GroupPolicy-Management-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 18.54 MB
- **Availability**: Windows 10, version 1809 and later

**Feature**: IP Address Management (IPAM) Client 
- **Description**: Used to connect to and manage a remote IPAM server
- **Dependencies**: Rsat.ServerManager.Tools 
- **Capability name**: Rsat.IPAM.Client.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-IPAM-Client-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 872.56 KB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Data Center Bridging LLDP Tools 
- **Description**: Includes PowerShell tools for remotely managing LLDP agents on Windows Server 
- **Capability name**: Rsat.LLDP.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-LLDP-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: None 
- **Install size**: 19.19 KB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Network Controller Management Tools 
- **Description**: PowerShell tools for managing the Network Controller role on Windows Server
- **Capability name**: Rsat.NetworkController.Tools~\~~\~0.0.1.0
- **CAB name**: Microsoft-Windows-NetworkController-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 767.20 KB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Network Load Balancing Tools
- **Description**: Network Load Balancing Manager snap-in, the Network Load balancing module for PowerShell, and the nlb.exe and wlbs.exe command-line tools 
- **Capability name**: Rsat.NetworkLoadBalancing.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-NetworkLoadBalancing-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 859.35 KB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Remote Access Management Tools 
- **Description**: Graphical and PowerShell tools for manging the Remote Access role on Windows Server
- **Dependencies**: Rsat.ServerManager.Tools, Rsat.GroupPolicy.Management.Tools 
- **Capability name**: Rsat.RemoteAccess.Management.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-RemoteAccess-Management-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 27.70 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Remote Desktop Services Tools 
- **Description**: Snap-ins for Remote Desktop Licensing Manager, Remote Desktop Licensing Diagnostics, and Remote Desktop Gateway Manager. 
- **Capability name**: Rsat.RemoteDesktop.Services.Tools~\~\~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-RemoteDesktop-Services-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 3.60 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Server Manager
- **Description**: Server Manager console and PowerShell tools for remotely managing Windows Server
- **Dependencies**: None. NICTeaming.Tools.Legacy is already merged with this package. 
- **Capability name**: Rsat.ServerManager.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-ServerManager-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 32.47 MB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Shielded VM Tools
- **Description**: Includes the Provisioning Data File Wizard and the Template Disk Wizard
- **Dependencies**: Rsat.ServerManager.Tools 
- **Capability name**: Rsat.Shielded.VM.Tools~\~~\~0.0.1.0
- **CAB name**: Microsoft-Windows-Shielded-VM-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 20.09 MB 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Storage Replica Module for Windows PowerShell 
- **Description**: Remotely manage the Storage Replica feature with PowerShell 
- **Capability name**: Rsat.StorageReplica.Tools~\~\~\~0.0.1.0
- **CAB name**: Microsoft-Windows-StorageReplica-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 1.58 MB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Volume Activation Tools
- **Description**: Manage volume activation license keys on a KMS host or in Microsoft AAD
- **Capability name**: Rsat.VolumeActivation.Tools~\~\~\~0.0.1.0
- **CAB name**: Microsoft-Windows-VolumeActivation-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Yes
- **Install size**: 556.39 KB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Windows Server Update Services Tools 
- **Description**: Includes graphical and PowerShell tools for managing WSUS 
- **Capability name**: Rsat.WSUS.Tools~\~\~\~0.0.1.0  
- **CAB name**: Microsoft-Windows-WSUS-Tools-FoD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Lang
- **Install size**: 8.27 MB
- **Availability**: Windows 10, version 1809 and later

**Feature**: Storage Migration Service Management Tools 
- **Description**: Provides management tools for storage migration jobs 
- **Capability name**: Rsat.StorageMigrationService.Management.Tools~\~~\~0.0.1.0
- **CAB name**: Microsoft-Windows-StorageMigrationService-Management-Tools-FOD-Package\~31bf3856ad364e35\~amd64~~.cab  
- **Satellites**: Yes
- **Install size**: 303.98 
- **Availability**: Windows 10, version 1809 and later

**Feature**: Systems Insights Module for Windows PowerShell
- **Description**: Provides the ability to manage the System Insights feature
- **Capability name**: Rsat.SystemInsights.Management.Tools~\~~\~0.0.1.0 
- **CAB name**: Microsoft-Windows-SystemInsights-Management-Tools-FOD-Package\~31bf3856ad364e35\~amd64~~.cab
- **Satellites**: Lang
- **Install size**: 123.43 KB
- **Availability**: Windows 10, version 1809 and later

### Storage

This Feature on Demand enables advanced storage capabilities. To add Windows Storage Management, you have to add both FODs to an image.

**Recommendation:** In general, OEMs shouldn’t preinstall this FOD. OEMs and IT pros can consider preinstalling this FOD when they are building a PC that requires advanced storage capabilities.

**Feature**: Windows Storage Management 
- **Description**: Windows Storage Management allows you to manage a wide range of storage configurations, from single-disk desktops to external storage arrays.
- **Capability name**: Microsoft.Windows.StorageManagement~\~~\~0.0.1.0
- **CAB name**: Microsoft-Windows-StorageManagement-FoD-Package\~31bf3856ad364e35\\~amd64~~.cab  
- **Satellites**: Yes
- **Install size**: 15.38 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1809 and later

**Feature**: Windows Storage Management 
- **CAB name**: Windows Storage Management allows you to manage a wide range of storage configurations, from single-disk desktops to external storage arrays.
- **Capability name**: Microsoft.OneCore.StorageManagement~\~~\~0.0.1.0	
- **CAB name**: Microsoft-OneCore-StorageManagement-FoD-Package\~31bf3856ad364e35\\~amd64\~\~.cab  
- **Satellites**: Yes
- **Install size**: 9.80 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1809 and later

### XPS Viewer

This Feature on Demand allows you to read, copy, print, sign, and set permissions for XPS documents.

**Recommendation:** In general, OEMs shouldn’t preinstall this FOD. OEMs and IT pros can consider preinstalling this FOD when they are building a PC that requires advance storage capabilities.

**Feature**: XPS Viewer 
- **Capability name**: XPS.Viewer~~~~0.0.1.0 
- **CAB name**: Microsoft-Windows-Xps-Xps-Viewer-Opt-Package\~31bf3856ad364e35\\~amd64\~\~.cab
- **Install size**: 16.91 MB
- **Satellites**: None
- **Availability**: Windows 10, version 1803 and later


## Related topics

[Features on Demand](features-on-demand-v2--capabilities.md) 

[Language and region Features on Demand](features-on-demand-language-fod.md)
