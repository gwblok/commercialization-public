---
title: ArchiveFaxes
description: ArchiveFaxes
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b9abc91a-50a7-47b4-b71b-77573541b35d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ArchiveFaxes


`ArchiveFaxes` indicates whether to save all incoming and outgoing faxes in a folder.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Indicates that incoming and outgoing faxes not assigned to a specific user are saved to a folder. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Indicates that incoming and outgoing faxes not assigned to a specific user are not saved to a folder.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md) | [Fax](microsoft-windows-fax-service-fax.md) | **ArchiveFaxes**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md).

## XML Example


The following XML output shows how to set fax settings.

```
<Fax>
   <ArchiveFaxes>false</ArchiveFaxes>
   <IncomingFaxesArePublic>false</IncomingFaxesArePublic>
   <ArchiveFolderName>C:\MyFaxArchives</ArchiveFolderName>
</Fax>
<FaxUnattend>
   <FaxPrinterIsShared>true</FaxPrinterIsShared>
   <ReceiveFaxes>false</ReceiveFaxes>
   <Rings>6</Rings>
   <RouteToFolder>true</RouteToFolder>
   <RouteToPrinter>true</RouteToPrinter>
   <SendFaxes>true</SendFaxes>
   <Csid>Fax1</Csid>
   <Tsid>Fax1</Tsid>
   <RouteFolderName>C:\Router</RouteFolderName>
   <RoutePrinterName>C:\Printer</RoutePrinterName>
</FaxUnattend>
<Receipts>
   <FaxUserName>MyUserName</FaxUserName>
   <FaxUserPassword>MyPassword</FaxUserPassword>
   <SmtpNotificationsEnabled>true</SmtpNotificationsEnabled>
   <SmtpSenderAddress>MyUserName@fabrikam.com</SmtpSenderAddress>
   <SmtpServerAddress>207.46.197.32</SmtpServerAddress>
   <SmtpServerAuthenticationMechanism>1</SmtpServerAuthenticationMechanism>
   <SmtpServerPort>26</SmtpServerPort>
</Receipts>
```

## Related topics


[Fax](microsoft-windows-fax-service-fax.md)

 

 







