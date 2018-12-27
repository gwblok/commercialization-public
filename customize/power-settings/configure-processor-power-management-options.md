---
title: Processor power management options
description: The Windows 10 processor power management (PPM) algorithms implement OS-level functionality that allows the OS to efficiently use the available processing resources on a platform by balancing the user's expectations of performance and energy efficiency.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 29605DF5-BEDC-423C-83E2-77AF8BE7A3D1


ms.date: 10/05/2017
ms.topic: article


---
# Processor power management options

The Windows 10 processor power management (PPM) algorithms implement OS-level functionality that allows the OS to efficiently use the available processing resources on a platform by balancing the user's expectations of performance and energy efficiency.

The algorithms have the following characteristics:

* They scale from big servers to tablet form factors.
* They are customizable through a statically configurable power policy infrastructure.
* They are hierarchical and abstracted in a manner that separates platform-agnostic portions of the algorithms from platform-specific portions.

At a high-level, the Windows PPM is made up of the following parts:

* **Core parking engine** - Makes global scalability decisions about the workload and determines the optimum set of compute cores to execute with.
* **Performance state engine** - Makes per-processor performance scaling decisions.
* **Platform specific controls** - Implements the mechanics of state transitions and optionally provides feedback about the effectiveness of OS state decisions and runtime platform constraints.

IHV partners can enable preliminary validation and measurement of the effects of the policy controls on different hardware configurations.

## <span id="Power_profiles"></span><span id="power_profiles"></span><span id="POWER_PROFILES"></span>Power profiles

You can use the Windows Provisioning framework to configure the processor power settings described in this section. First, create a provisioning package using [Windows Configuration Designer](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-install-icd). You will then edit the customizations.xml file contained in the package to include your power settings, which appear under the `Common\Power\Policy\Settings\Processor` namespace. Use the XML file as one of the inputs to the Windows Configuration Designer command-line interface to generate either a provisioning package that contains the power settings. You can then apply the provisioning package to the image. For information on how to use the Windows Configuration Designer CLI, see [Use the Windows Configuration Designer command-line interface](https://docs.microsoft.com/en-us/windows/configuration/provisioning-packages/provisioning-command-line).

The processor namespace is divided into three sets of identical power processor configurations called power profiles. The power profiles are used by the power processor engine to adapt the performance and parking algorithm on various system use cases.

Windows 10 supports the following profiles:

* *Default* profile is the configuration set that is active most of the time.
* *LowLatency* is the profile that is activated during boot and during app launch time.
* *LowPower* is the profile that is activated during the buffering phase of media playback scenarios.
* *Constrained* is a profile activated by the battery saver feature on Windows 10 for desktop editions (Home, Pro, Enterprise, and Education). This is not available on Windows 10 Mobile.

Each profile supports the following configuration settings:

* [CPMinCores](options-for-core-parking-cpmincores.md)
* [CPMaxCores](options-for-core-parking-cpmaxcores.md)
* [CPIncreaseTime](options-for-core-parking-cpincreasetime.md)
* [CPDecreaseTime](options-for-core-parking-cpdecreasetime.md)
* [CPConcurrency](options-for-core-parking-cpconcurrency.md)
* [CPDistribution](options-for-core-parking-cpdistribution.md)
* [CPHeadroom](options-for-core-parking-cpheadroom.md)
* [CpLatencyHintUnpark](options-for-core-parking-cplatencyhintunpark.md)
* [MaxPerformance](options-for-perf-state-engine-maxperformance.md)
* [MinPerformance](options-for-perf-state-engine-minperformance.md)
* [PerfIncreaseThreshold](options-for-perf-state-engine-perfincreasethreshold.md)
* [PerfIncreaseTime](options-for-perf-state-engine-perfincreasetime.md)
* [PerfDecreaseThreshold](options-for-perf-state-engine-perfdecreasethreshold.md)
* [PerfDecreaseTime](options-for-perf-state-engine-perfdecreasetime.md)
* [PerfLatencyHint](options-for-perf-state-engine-perflatencyhint.md)
* [PerfAutonomousMode](options-for-perf-state-engine-perfautonomousmode.md)
* [PerfEnergyPreference](options-for-perf-state-engine-perfenergypreference.md)

On systems with processors with heterogeneous architecture, the configuration settings for efficiency class 1 cores use a similar naming convention. Efficiency class is defined in ACPI 6.0 section 5.2.12.14 GICC Structure. For more information, consult the ACPI specification.

The common parameters have the suffix "1" to indicate efficiency class. Hetero-specific parameters have the prefix "Hetero".

* [CPMinCores1](options-for-core-parking-cpmincores.md)
* [CPMaxCores1](options-for-core-parking-cpmaxcores.md)
* [HeteroIncreaseTime](configuration-for-hetero-power-scheduling-heteroincreasetime.md)
* [HeteroDecreaseTime](configuration-for-hetero-power-scheduling-heterodecreasetime.md)
* [HeteroIncreaseThreshold](configuration-for-hetero-power-scheduling-heteroincreasethreshold.md)
* [HeteroDecreaseThreshold](configuration-for-hetero-power-scheduling-heterodecreasethreshold.md)
* [CpLatencyHintUnpark1](options-for-core-parking-cplatencyhintunpark.md)
* [MaxPerformance1](options-for-perf-state-engine-maxperformance.md)
* [MinPerformance1](options-for-perf-state-engine-minperformance.md)
* [PerfIncreaseThreshold1](options-for-perf-state-engine-perfincreasethreshold.md)
* [PerfIncreaseTime1](options-for-perf-state-engine-perfincreasetime.md)
* [PerfDecreaseThreshold1](options-for-perf-state-engine-perfdecreasethreshold.md)
* [PerfDecreaseTime1](options-for-perf-state-engine-perfdecreasetime.md)
* [PerfLatencyHint1](options-for-perf-state-engine-perflatencyhint.md)
* [HeteroClass1InitialPerf](configuration-for-hetero-power-scheduling-heteroclass1initialperf.md)
* [HeteroClass0FloorPerf](configuration-for-hetero-power-scheduling-heteroclass0floorperf.md)
