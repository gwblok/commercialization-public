---
title: IpAddress
description: IpAddress
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1d781eec-97b7-4522-a920-9d9c93e7833b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# IpAddress

`IpAddress` specifies an IP address that is a member of [NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md).

> [!Note]
> The child elements do not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add this element to the answer file.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress-key.md) | Specifies a unique key for the IP address. |
| [Value](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress-value.md) | Specifies the value of the IP address. |
 
This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetBT](microsoft-windows-netbt.md) | [Interfaces](microsoft-windows-netbt-interfaces.md) | [Interface](microsoft-windows-netbt-interfaces-interface.md) | [NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md) | **IpAddress**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetBT](microsoft-windows-netbt.md).

## XML Example

The following XML output shows how to configure microsoft-windows-netbt-.

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

[NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md)
