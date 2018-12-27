---
title: Interface
description: Interface
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 67491f8a-22bf-47be-882a-5e7d52d85b92
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Interface

`Interface` specifies settings for a particular interface.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Identifier](microsoft-windows-netbt-interfaces-interface-identifier.md) | Specifies the interface to apply to other settings in <code>Interface</code>. |
| [NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md) | Specifies the list of name servers. |
| [NetbiosOptions](microsoft-windows-netbt-interfaces-interface-netbiosoptions.md) | Specifies security settings for the NetBIOS service. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetBT](microsoft-windows-netbt.md) | [Interfaces](microsoft-windows-netbt-interfaces.md) | **Interface**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetBT](microsoft-windows-netbt.md).

## XML Example

The following XML output shows how to configure Microsoft-Windows-NetBT.

```XML
<Interfaces>
   <Interface wcm:action="add">
      <NameServerList>
         <IpAddress wcm:action="add" wcm:keyValue="IpAddress1">123.45.67.89</IpAddress>
         <IpAddress wcm:action="add" wcm:keyValue="IpAddress2">56.78.90.123</IpAddress>
       </NameServerList>
       <NetbiosOptions>2</NetbiosOptions>
       <Identifier>Local Area Connection</Identifier>
   </Interface>
</Interfaces>
```

## Related topics

[Interfaces](microsoft-windows-netbt-interfaces.md)
