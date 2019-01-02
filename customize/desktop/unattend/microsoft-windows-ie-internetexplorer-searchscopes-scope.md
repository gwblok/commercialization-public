---
title: Scope
description: Scope
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: beac7cab-43ea-41c3-8af0-6d1a75f1dc74
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Scope

`Scope` specifies a search provider.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FaviconURL](microsoft-windows-ie-internetexplorer-searchscopes-scope-faviconurl.md) | Specifies the path to an icon for a specific Search Scope item. Internet Explorer 8 through Internet Explorer 11. |
| [PreviewURL](microsoft-windows-ie-internetexplorer-searchscopes-scope-previewurl.md) | Specifies the URL where previews are shown in the <strong>Accelerator</strong> window. Internet Explorer 8 through Internet Explorer 11. |
| [ScopeDefault](microsoft-windows-ie-internetexplorer-searchscopes-scope-scopedefault.md) | Specifies whether the Search Scope item is the default search provider. Internet Explorer 7 through Internet Explorer 11. |
| [ScopeDisplayName](microsoft-windows-ie-internetexplorer-searchscopes-scope-scopedisplayname.md) | Specifies the display name for the search provider. Internet Explorer 7 through Internet Explorer 11. |
| [ScopeKey](microsoft-windows-ie-internetexplorer-searchscopes-scope-scopekey.md) | Specifies the unique string for the search provider. Internet Explorer 7 through Internet Explorer 11. |
| [ScopeUrl](microsoft-windows-ie-internetexplorer-searchscopes-scope-scopeurl.md) | Specifies the URL for the search provider. Internet Explorer 7 through Internet Explorer 11. |
| [ShowSearchSuggestions](microsoft-windows-ie-internetexplorer-searchscopes-scope-showsearchsuggestions.md) | Specifies whether Search Suggestions are shown. Internet Explorer 8 through Internet Explorer 11. |
| [SuggestionsURL](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl.md) | Specifies suggestions that appear to the user during a search, by using a search that is based on XML. Internet Explorer 8 through Internet Explorer 11. |
| [SuggestionsURL_JSON](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl-json.md) | Specifies suggestions that appear to the user during a search, by using a search that is based on JavaScript Object Notation (JSON). Internet Explorer 8 through Internet Explorer 11. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [SearchScopes](microsoft-windows-ie-internetexplorer-searchscopes.md) | **Scope**

## Applies To

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

[SearchScopes](microsoft-windows-ie-internetexplorer-searchscopes.md)
