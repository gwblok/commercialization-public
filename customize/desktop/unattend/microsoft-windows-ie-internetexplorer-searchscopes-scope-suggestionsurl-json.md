---
title: SuggestionsURL\_JSON
description: SuggestionsURL\_JSON
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a220f091-5364-476b-8c17-5271fdd39848
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SuggestionsURL\_JSON


The `SuggestionsURL_JSON` setting specifies the URL where search suggestions can be retrieved by using a search based on JavaScript Object Notation (JSON).

**Note**  
To specify search suggestions by using a search based on XML, use the [SuggestionsURL](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl.md) instead.

 

For information on creating Search Scopes, see [Search Provider Extensibility](http://go.microsoft.com/fwlink/?LinkId=137666).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>URL</em></p></td>
<td><p>Specifies the URL where search suggestions can be retrieved by using a search based on JavaScript Object Notation (JSON).</p>
<p><em>URL</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [SearchScopes](microsoft-windows-ie-internetexplorer-searchscopes.md) | [Scope](microsoft-windows-ie-internetexplorer-searchscopes-scope.md) | `SuggestionsURL_JSON`

## Applies To


For a list of the supported Microsoft Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML example shows how to specify a URL to provide search suggestions by using a search based on JavaScript Object Notation (JSON).

```
 
<SearchScopes>
   <Scope wcm:action="add">
      <ScopeDefault>true</ScopeDefault>
      <ScopeDisplayName>MyFirstSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider1</ScopeKey>
      <ScopeUrl>http://www.contoso.com/search?q={searchTerms}</ScopeUrl>
      <SuggestionsURL_JSON>http://suggestions.contoso.com/search?&search={searchTerms}</SuggestionsURL_JSON>
      <DisplayQuickPick>false</DisplayQuickPick>
   </Scope>
</SearchScopes>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[SuggestionsURL](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl.md)

 

 







