---
title: Querying Providers
description: Querying Providers
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: abe58e3b-4050-4d42-ad71-a0c702492f8d
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# Querying Providers


Displays trace and providers query options.

```
xperf {-providers [options] | -loggers | -boottrace | -profint | -profiles | -profileswithdetails | -profilesessions | -profileproviders | -profileloggers}
```

## Parameters


<a href="" id="-providers-options----"></a>**-providers**<em>\[options...\]</em>  
Query all installed/known and registered providers, as well as all known kernel flags and groups. For details, see [providers](providers-wpa.md).

<a href="" id="-loggers"></a>**-loggers**  
Query all active logging sessions.

<a href="" id="-boottrace"></a>**-boottrace**  
Query the boot trace configuration.

<a href="" id="-profint"></a>**-profint**  
Query the current profile interval.

<a href="" id="-profiles-profilefilename---profilename-"></a>**-profiles**<em>{ProfileFileName | ProfileName}</em>  
Query the profile names defined in *ProfileFileName* or *ProfileName*. If no parameters are specified, query the names of the built-in profiles.

<a href="" id="-profileswithdetails-profilefilename---profilename-"></a>**-profileswithdetails**<em>{ProfileFileName | ProfileName}</em>  
Query the profile names defined in *ProfileFileName* or detailed properties in *ProfileName*. If no parameters are specified, query the names of the built-in profiles.

<a href="" id="-profilesessions-profilefilename---sessionname-"></a>**-profilesessions**<em>{ProfileFileName | SessionName}</em>  
Query the profile session names defined in *ProfileFileName* or *SessionName*. If no parameters are specified, query the names of the built-in profile sessions.

<a href="" id="-profileproviders-profilefilename---providername-"></a>**-profileproviders**<em>{ProfileFileName | ProviderName}</em>  
Query the profile provider names defined in *ProfileFileName* or *ProviderName*. If no parameters are specified, query the names of the built-in profile providers.

<a href="" id="-profileloggersprofilename"></a>**-profileloggers***ProfileName*  
Query logging sessions specified in *ProfileName*.

## Related topics


[Xperf Options](xperf-options.md)

 

 







