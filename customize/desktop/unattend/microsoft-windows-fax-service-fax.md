---
title: Fax
description: Fax
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: adde805b-4b74-4858-902a-5c1eed96de84
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Fax

`Fax` specifies settings for saving incoming and outgoing faxes and whether incoming faxes can be viewed by all users.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ArchiveFaxes](microsoft-windows-fax-service-fax-archivefaxes.md) | Specifies whether to save all incoming and outgoing faxes in a folder. |
| [ArchiveFolderName](microsoft-windows-fax-service-fax-archivefoldername.md) | Specifies the folder in which the fax service saves copies of all incoming and outgoing faxes. |
| [IncomingFaxesArePublic](microsoft-windows-fax-service-fax-incomingfaxesarepublic.md) | Specifies whether all incoming faxes not assigned to a specific user can be viewed by all users. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md) | **Fax**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md).

## XML Example

The following XML output shows how to set fax settings.

```XML
<Fax>
   <ArchiveFaxes>true</ArchiveFaxes>
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
