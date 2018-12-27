---
title: ShowSearchSuggestions
description: ShowSearchSuggestions
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9b5d9c27-66e5-492b-b7c6-d562e7ee67dd
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ShowSearchSuggestions


`ShowSearchSuggestions` specifies whether Search Suggestions are shown in Windows Internet Explorer.

When Search Suggestions are shown, a menu appears below the search box with suggestions when a user types a search into the Internet Explorer Search box.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Specifies that Search Suggestions are shown.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Specifies that Search Suggestions are not shown.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [SearchScopes](microsoft-windows-ie-internetexplorer-searchscopes.md) | [Scope](microsoft-windows-ie-internetexplorer-searchscopes-scope.md) | `ShowSearchSuggestions`

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to hide the Search Suggestions.

```
<SearchScopes>
   <Scope wcm:action="add">
      <ScopeDefault>true</ScopeDefault>
      <ScopeDisplayName>MyFirstSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider1</ScopeKey>
      <ScopeUrl>http://www.contoso.com/search?q={searchTerms}</ScopeUrl>
      <ShowSearchSuggestions>false</ShowSearchSuggestions>
   </Scope>
   <Scope wcm:action="add">
      <ScopeDisplayName>MySecondSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider2</ScopeKey>
      <ScopeUrl>http://search.fabrikam.com/results.aspx?q=&quot;{searchTerms}&quot;</ScopeUrl>
      <ShowSearchSuggestions>false</ShowSearchSuggestions>
   </Scope>
</SearchScopes>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







