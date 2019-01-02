---
title: SuggestionsURL
description: SuggestionsURL
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a7163e33-d03e-465d-9d81-af0abf47e83f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SuggestionsURL


The `SuggestionsURL` setting specifies the URL where suggestions can be retrieved by using a search based on XML.

**Note**  
To specify search suggestions by using a search based on JavaScript Object Notation (JSON), use the [SuggestionsURL\_JSON](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl-json.md) setting instead.

 

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
<td><p>Specifies the URL where search suggestions can be retrieved by using a search based on XML.</p>
<p><em>URL</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [SearchScopes](microsoft-windows-ie-internetexplorer-searchscopes.md) | [Scope](microsoft-windows-ie-internetexplorer-searchscopes-scope.md) | `SuggestionsURL`

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to specify a URL to provide search suggestions by using a search based on XML.

```
<SearchScopes>
   <Scope wcm:action="add">
      <ScopeDisplayName>MySecondSearchProvider</ScopeDisplayName>
      <ScopeKey>SearchProvider2</ScopeKey>
      <ScopeUrl>http://search.fabrikam.com/results.aspx?q=&quot;{searchTerms}&quot;</ScopeUrl>
      <SuggestionsURL>http://suggestions.fabrikam.com/qsml.aspx?query={searchTerms}</SuggestionsURL>
   </Scope>
</SearchScopes>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[SuggestionsURL\_JSON](microsoft-windows-ie-internetexplorer-searchscopes-scope-suggestionsurl-json.md)

 

 







