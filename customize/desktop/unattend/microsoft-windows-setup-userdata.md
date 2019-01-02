---
title: UserData
description: UserData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 24c2c860-ac2e-47c4-9a67-0d1dd3a3b364
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# UserData

`UserData` specifies user settings.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AcceptEula](microsoft-windows-setup-userdata-accepteula.md) | Specifies whether to automatically accept the Microsoft Software License Terms. |
| [FullName](microsoft-windows-setup-userdata-fullname.md) | Specifies the name of the end user. |
| [Organization](microsoft-windows-setup-userdata-organization.md) | Specifies the name of the organization that owns the computer. |
| [ProductKey](microsoft-windows-setup-userdata-productkey.md) | Specifies the product key to use, which determines the edition of Windows to install. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **UserData**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set user data.

```XML
<UserData>
   <AcceptEula>true</AcceptEula>
   <FullName>EndUserName</FullName>
   <Organization>Fabrikam</Organization>
   <ProductKey>
      <Key>12345-12345-12345-12345-12345</Key>
      <WillShowUI>Never</WillShowUI>
   </ProductKey>
</UserData>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
