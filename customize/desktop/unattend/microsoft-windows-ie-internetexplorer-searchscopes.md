---
title: SearchScopes
description: SearchScopes
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c616d4b3-1133-47a8-8824-dde8e7c95342
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# SearchScopes

`SearchScopes` specifies Internet search providers.

During unattended installation, **SearchScopes** adds search providers to the default list of search providers, but does not overwrite user-chosen providers.

> [!Note]
> If the user performs an upgrade to the operating system, the existing search providers from the previous operating system installation are maintained. The search providers that the unattended-installation answer file specifies are applied only when the user clicks **Restore Defaults**.
 
## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Scope](microsoft-windows-ie-internetexplorer-searchscopes-scope.md) | Specifies a search provider. |
 
## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **SearchScopes**

## Applies To

For a list of which Search Scope settings are available in each version of Internet Explorer, see [Scope](microsoft-windows-ie-internetexplorer-searchscopes-scope.md).

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following example shows how to set search providers.

```XML
<SearchScopes>
   <Scope wcm:action="add">
      <ScopeDefault>true</ScopeDefault>
      <ScopeDisplayName>MyFirstSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider1</ScopeKey>
      <ScopeUrl>http://www.contoso.com/search?q={searchTerms}</ScopeUrl>
   </Scope>
   <Scope wcm:action="add">
      <ScopeDisplayName>MySecondSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider2</ScopeKey>
      <ScopeUrl>http://search.fabrikam.com/results.aspx?q=&quot;{searchTerms}&quot;</ScopeUrl>
   </Scope>
</SearchScopes>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)
