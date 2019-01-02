---
title: Elements
description: Elements
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 93024039-529c-439f-9c91-f6174f4a91e7
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 9/29/2017
ms.topic: article


---


# Elements

The following represents the element hierarchy.

* <[WindowsPerformanceRecorder](windowsperformancerecorder.md)>
  * <[Profiles](profiles.md)>
    * <[SystemCollector](systemcollector.md)>
      * <[BufferSize](buffersize.md)>
      * <[Buffers](buffers.md)>
      * <[StackCaching](stackcaching.md)>
    * <[EventCollector](eventcollector.md)>
      * <[BufferSize](buffersize.md)>
      * <[Buffers](buffers.md)>
      * <[StackCaching](stackcaching.md)>
    * <[HeapEventCollector](heapeventcollector.md)>
      * <[BufferSize](buffersize.md)>
      * <[Buffers](buffers.md)>
      * <[StackCaching](stackcaching.md)>
    * <[SystemProvider](systemprovider.md)>
      * <[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)>
        * <[Keyword (in SystemProvider)](keyword--in-systemprovider-.md)>
        * <[CustomKeyword](customkeyword.md)>
      * <[Stacks](stacks.md)>
        * <[Stack](stack-wpa.md)>
      * <[PoolTags](pooltags.md)>
        * <[PoolTag](pooltag.md)>
    * <[EventProvider](eventprovider.md)>
      * <[Keywords (in EventProvider)](keywords--in-eventprovider-.md)>
        * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
      * <[CaptureStateOnStart](capturestateonstart.md)>
        * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
      * <[CaptureStateOnSave](capturestateonsave.md)>
        * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
    * <[HeapEventProvider](heapeventprovider.md)>
      * <[HeapProcessIds](heapprocessids.md)>
        * <[HeapProcessId](heapprocessid.md)>
    * <[Profile](profile-wpr.md)>
      * <[ProblemCategories](problemcategories.md)>
        * <[ProblemCategory](problemcategory.md)>
      * <[Collectors](collectors.md)>
        * <[SystemCollectorId](systemcollectorid.md)>
          * <[BufferSize](buffersize.md)>
          * <[Buffers](buffers.md)>
          * <[StackCaching](stackcaching.md)>
          * <[SystemProviderId](systemproviderid.md)>
            * <[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)>
              * <[Keyword (in SystemProvider)](keyword--in-systemprovider-.md)>
              * <[CustomKeyword](customkeyword.md)>
            * <[Stacks](stacks.md)>
              * <[Stack](stack-wpa.md)>
            * <[PoolTags](pooltags.md)>
              * <[PoolTag](pooltag.md)>
          * <[SystemProvider](systemprovider.md)>
            * <[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)>
              * <[Keyword (in SystemProvider)](keyword--in-systemprovider-.md)>
              * <[CustomKeyword](customkeyword.md)>
            * <[Stacks](stacks.md)>
              * <[Stack](stack-wpa.md)>
            * <[PoolTags](pooltags.md)>
              * <[PoolTag](pooltag.md)>
        * <[EventCollectorId](eventcollectorid.md)>
          * <[BufferSize](buffersize.md)>
          * <[Buffers](buffers.md)>
          * <[StackCaching](stackcaching.md)>
          * <[EventProviders](eventproviders.md)>
            * <[EventProviderId](eventproviderid.md)>
              * <[Keywords (in EventProvider)](keywords--in-eventprovider-.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
              * <[CaptureStateOnStart](capturestateonstart.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
              * <[CaptureStateOnSave](capturestateonsave.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
            * <[EventProvider](eventprovider.md)>
              * <[Keywords (in EventProvider)](keywords--in-eventprovider-.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
              * <[CaptureStateOnStart](capturestateonstart.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
              * <[CaptureStateOnSave](capturestateonsave.md)>
                * <[Keyword (in EventProvider)](keyword--in-eventprovider-.md)>
        * <[HeapEventCollectorId](heapeventcollectorid.md)>
          * <[BufferSize](buffersize.md)>
          * <[Buffers](buffers.md)>
          * <[StackCaching](stackcaching.md)>
          * <[HeapEventProviders](heapeventproviders.md)>
            * <[HeapEventProviderId](heapeventproviderid.md)>
              * <[HeapProcessIds](heapprocessids.md)>
                * <[HeapProcessId](heapprocessid.md)>
            * <[HeapEventProvider](heapeventprovider.md)>
              * <[HeapProcessIds](heapprocessids.md)>
                * <[HeapProcessId](heapprocessid.md)>
  * <[TraceMergeProperties](tracemergeproperties.md)>
    * <[TraceMergeProperty](tracemergeproperty.md)>
      * <[DeletePreMergedTraceFiles](deletepremergedtracefiles.md)>
      * <[CustomEvents](customevents.md)>
        * <[CustomEvent](customevent.md)>
      * <[FileCompression](filecompression.md)>
  * <[OnOffTransitionConfigurations](onofftransitionconfigurations.md)>
    * <[OnOffTransitionConfiguration](onofftransitionconfiguration.md)>
      * <[PrepareSystem](preparesystem.md)>
      * <[NumberOfRuns](numberofruns.md)>
      * <[PostBootDelay](postbootdelay.md)>
      * <[WakeupDelay](wakeupdelay.md)>
      * <[TransitionTag](transitiontag.md)>

This following section describes the elements that you can use to author recording profiles for Windows Performance Recorder (WPR).


## In This Section

| Element                                                           | Description                                                                                                                                                                                                                     |
| :---------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Buffers](buffers.md)                                             | Describes either the number of buffers to be allocated when starting a session or the percentage of total memory that should be allocated for the session, depending on the value of the **PercentageOfTotalMemory** attribute. |
| [BufferSize](buffersize.md)                                       | Describes the size of each buffer, in KB.                                                                                                                                                                                       |
| [CaptureStateOnSave](capturestateonsave.md)                       | Represents a collection of keywords that describe the events to be captured when a trace is saved.                                                                                                                              |
| [CaptureStateOnStart](capturestateonstart.md)                     | Represents a collection of keywords that describe the events to be captured at the start of a recording.                                                                                                                        |
| [Collectors](collectors.md)                                       | Represents a collection of system collector identifiers, event collector identifiers, and optionally heap event collector identifiers.                                                                                          |
| [CustomEvent](customevent.md)                                     | Represents a custom event.                                                                                                                                                                                                      |
| [CustomEvents](customevents.md)                                   | Represents a collection of custom events.                                                                                                                                                                                       |
| [CustomKeyword](customkeyword.md)                                 | Represents a custom keyword for the profile.                                                                                                                                                                                    |
| [DeletePreMergedTraceFiles](deletepremergedtracefiles.md)         | Indicates whether to delete premerged event trace log (ETL) files.                                                                                                                                                             |
| [EventCollector](eventcollector.md)                               | Represents an event collector for the profile.                                                                                                                                                                                  |
| [EventCollectorId](eventcollectorid.md)                           | Represents an event collector identifier for the profile.                                                                                                                                                                       |
| [EventProvider](eventprovider.md)                                 | Configures the Event Tracing for Windows (ETW) user-mode provider.                                                                                                                                                              |
| [EventProviderId](eventproviderid.md)                             | Represents an event provider identifier for the profile.                                                                                                                                                                        |
| [EventProviders](eventproviders.md)                               | Represents a collection of event provider identifiers and event providers.                                                                                                                                                      |
| [FileCompression](filecompression.md)                             | Indicates whether to compress the ETL file.                                                                                                                                                                                     |
| [HeapEventCollector](heapeventcollector.md)                       | Represents a collector for heap events.                                                                                                                                                                                         |
| [HeapEventCollectorId](heapeventcollectorid.md)                   | Represents an identifier for a collector of heap events for the profile.                                                                                                                                                        |
| [HeapEventProvider](heapeventprovider.md)                         | Represents a provider of heap events for the profile.                                                                                                                                                                           |
| [HeapEventProviderId](heapeventproviderid.md)                     | Represents an identifier for a provider of heap events.                                                                                                                                                                         |
| [HeapEventProviders](heapeventproviders.md)                       | Represents a collection of heap event provider identifiers and heap event providers.                                                                                                                                            |
| [HeapProcessId](heapprocessid.md)                                 | Uniquely identifies a heap process.                                                                                                                                                                                             |
| [HeapProcessIds](heapprocessids.md)                               | Represents a collection of heap process identifiers.                                                                                                                                                                            |
| [Keyword (in EventProvider)](keyword--in-eventprovider-.md)       | Describes the ETW keyword for a user-mode provider.                                                                                                                                                                             |
| [Keyword (in SystemProvider)](keyword--in-systemprovider-.md)     | Describes the kernel flags that can be enabled for the kernel-mode session.                                                                                                                                                     |
| [Keywords (in EventProvider)](keywords--in-eventprovider-.md)     | Represents a collection of event provider keywords.                                                                                                                                                                             |
| [Keywords (in SystemProvider)](keywords--in-systemprovider-.md)   | Represents a collection of system provider keywords.                                                                                                                                                                            |
| [NumberOfRuns](numberofruns.md)                                   | Indicates the number of times that an on/off transition is run.                                                                                                                                                                 |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md)   | Represents an on/off transition configuration.                                                                                                                                                                                  |
| [OnOffTransitionConfigurations](onofftransitionconfigurations.md) | Represents a collection of on/off transition configurations.                                                                                                                                                                    |
| [PoolTag](pooltag.md)                                             | Describes the pool tags to be enabled for analyzing pool pages.                                                                                                                                                                 |
| [PoolTags](pooltags.md)                                           | Represents a collection of a maximum of four pool tags.                                                                                                                                                                         |
| [PostBootDelay](postbootdelay.md)                                 | Indicates the length of the delay, in seconds, after booting for an on/off transition.                                                                                                                                  |
| [PrepareSystem](preparesystem.md)                                 | Indicates whether to prepare the system for an on/off transition.                                                                                                                                                               |
| [ProblemCategories](problemcategories.md)                         | Represents a collection of problem categories.                                                                                                                                                                                  |
| [ProblemCategory](problemcategory.md)                             | Represents a problem category for the profile.                                                                                                                                                                                  |
| [Profile](profile-wpr.md)                                         | Represents a collection of problem categories and collectors.                                                                                                                                                                   |
| [Profiles](profiles.md)                                           | Represents a collection of collectors, providers, and profiles.                                                                                                                                                                 |
| [Stack](stack-wpa.md)                                             | Describes the kernel events on which stacks are to be enabled.                                                                                                                                                                  |
| [StackCaching](stackcaching.md)                                   | Describes stack caching attributes of collectors.                                                                                                                                                                               |
| [Stacks](stacks.md)                                               | Represents a collection of stacks.                                                                                                                                                                                              |
| [SystemCollector](systemcollector.md)                             | Describes the configurations to enable the ETW kernel-mode session.                                                                                                                                 |
| [SystemCollectorId](systemcollectorid.md)                         | Represents the identifier of a system collector.                                                                                                                                                                                |
| [SystemProvider](systemprovider.md)                               | Describes the configuration to enable the kernel-mode provider.                                                                                                                                                                 |
| [SystemProviderId](systemproviderid.md)                           | Uniquely identifies the system provider.                                                                                                                                                                                        |
| [TraceMergeProperties](tracemergeproperties.md)                   | Represents a collection of trace merge properties.                                                                                                                                                                              |
| [TraceMergeProperty](tracemergeproperty.md)                       | Contains configurations that are applied when recordings from multiple profiles are merged.                                                                                                                                     |
| [TransitionTag](transitiontag.md)                                 | Indicates the transition tag for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.                                                                                                                    |
| [WakeupDelay](wakeupdelay.md)                                     | Indicates the delay, in seconds, when emerging from a sleep state for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.                                                                               |
| [WindowsPerformanceRecorder](windowsperformancerecorder.md)       | Represents metadata about the authoring of profiles.                                                                                                                                                                            |


## Related topics

[Recording Profile XML Reference](recording-profile-xml-reference.md)

