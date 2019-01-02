---
title: Receipts
description: Receipts
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b8bc8d3c-599b-40ed-87f3-d4f6c0438690
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Receipts

`Receipts` specifies Simple Mail Transfer Protocol (SMTP) settings for faxes.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FaxUserName](microsoft-windows-fax-service-receipts-faxusername.md) | Specifies the account name to use for basic SMTP authentication or authentication based on Windows Security. |
| [FaxUserPassword](microsoft-windows-fax-service-receipts-faxuserpassword.md) | Specifies the password to use for authenticating against the server in basic SMTP authentication or authentication based on Windows Security. |
| [SmtpNotificationsEnabled](microsoft-windows-fax-service-receipts-smtpnotificationsenabled.md) | Specifies whether to enable SMTP notifications for outgoing faxes. |
| [SmtpSenderAddress](microsoft-windows-fax-service-receipts-smtpsenderaddress.md) | Specifies the e-mail address used in outgoing e-mail notifications. |
| [SmtpServerAddress](microsoft-windows-fax-service-receipts-smtpserveraddress.md) | Specifies the name or IP address of the e-mail server used to send and to receive faxes. |
| [SmtpServerAuthenticationMechanism](microsoft-windows-fax-service-receipts-smtpserverauthenticationmechanism.md) | Specifies one of the authentication schemas to use: Anonymous, Basic, or authentication based on Windows Security. |
| [SmtpServerPort](microsoft-windows-fax-service-receipts-smtpserverport.md) | Specifies the IP port number for the e-mail server. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md) | **Receipts**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md).

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
