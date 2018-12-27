---
title: LicensingMode
description: LicensingMode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 67efd87d-15da-49d5-ac05-20679fd6f8bf
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LicensingMode


`LicensingMode` configures how Terminal Services manages Client Access Licenses (CALs). Two types of Terminal Server Client Access Licenses are available: TS Device CAL or TS User CAL:

-   A Terminal Services Device CAL permits one device (used by any user) to conduct Windows Sessions on any of your servers.

-   A Terminal Services User CAL permits one user (by using any device) to conduct Windows Sessions on any of your servers.

**Note**  
This setting is ignored unless the Windows Feature **AppServer** **(Terminal Services Application Server)** is enabled in the Windows image.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>2</strong></p></td>
<td><p>CALs are configured Per Device</p>
<p>Configures Terminal Server to require that each connected client computer has a valid Terminal Server Client Access License (CAL). If the client computer has a Terminal Server CAL, it can access more than one Terminal Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>4</strong></p></td>
<td><p>CALs are configured Per Session</p>
<p>Configures Terminal Server to provide one Terminal Server CAL for each active client session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>5</strong></p></td>
<td><p><code>LicensingMode</code> is not configured</p></td>
</tr>
</tbody>
</table>

 

**Important**  
LicensingMode is an integer. If you enter a value that is not supported, the Remote Connection Manager will not be configured properly. Ensure that the value for this setting matches one of the supported values.

 

## Valid Configuration Passes


generalize

offlineServicing

specialize

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-RemoteConnectionManager](microsoft-windows-terminalservices-remoteconnectionmanager.md) | **LicensingMode**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-RemoteConnectionManager](microsoft-windows-terminalservices-remoteconnectionmanager.md).

## XML Example


```
<LicensingMode>2</LicensingMode>
```

## Related topics


[Microsoft-Windows-TerminalServices-RemoteConnectionManager](microsoft-windows-terminalservices-remoteconnectionmanager.md)

 

 







