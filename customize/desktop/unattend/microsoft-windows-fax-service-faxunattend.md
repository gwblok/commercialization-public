---
title: FaxUnattend
description: FaxUnattend
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f4ae8d99-6d03-4373-abad-2bfec81f4b4e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# FaxUnattend

`FaxUnattend` specifies details about sending, receiving, printing, and saving faxes.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Csid](microsoft-windows-fax-service-faxunattend-csid.md) | Specifies the called subscriber ID (CSID) transmitted to the sending fax machine when receiving incoming faxes. |
| [FaxPrinterIsShared](microsoft-windows-fax-service-faxunattend-faxprinterisshared.md) | Specifies if the fax printer is shared and if remote users can use the server as a shared fax server. |
| [ReceiveFaxes](microsoft-windows-fax-service-faxunattend-receivefaxes.md) | Specifies whether the fax service answers incoming calls on a device. This entry applies to existing and new fax devices. |
| [Rings](microsoft-windows-fax-service-faxunattend-rings.md) | Specifies the number of rings before the fax service answers the telephone. This entry applies to existing and new fax devices. |
| [RouteFolderName](microsoft-windows-fax-service-faxunattend-routefoldername.md) | Specifies the folder name to which the fax service automatically routes and saves incoming faxes. |
| [RoutePrinterName](microsoft-windows-fax-service-faxunattend-routeprintername.md) | Specifies the printer name to which the fax service routes (prints) incoming faxes automatically. |
| [RouteToFolder](microsoft-windows-fax-service-faxunattend-routetofolder.md) | Specifies whether to route incoming faxes to a folder. |
| [RouteToPrinter](microsoft-windows-fax-service-faxunattend-routetoprinter.md) | Specifies whether to route incoming faxes to a printer. |
| [SendFaxes](microsoft-windows-fax-service-faxunattend-sendfaxes.md) | Specifies whether the fax service uses a device to send faxes. This entry applies to existing and new fax devices. |
| [Tsid](microsoft-windows-fax-service-faxunattend-tsid.md) | Specifies the transmitting subscriber ID (TSID) sent by the fax device to a receiving fax machine. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md) | **FaxUnattend**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md).

## XML Example

The following XML output shows how to set fax settings.

```XML
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

[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md)
