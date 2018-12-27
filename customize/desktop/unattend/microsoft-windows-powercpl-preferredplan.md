---
title: PreferredPlan
description: PreferredPlan
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 22f41cd2-9293-4d3a-be91-93254eb094da
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PreferredPlan


`PreferredPlan` enables you to specify a plan for the computer's power settings. You can specify the power plan by using a Globally Unique Identifier (GUID) for an existing power plan. The specified power plan determines the default values for power-management settings, including the following settings:

-   The power button setting

-   The sleep button setting

-   The lid switch setting

-   The password-on-resume setting

The power plan also specifies icons on the **Global Settings Task** page for the power button, the sleep button, and the lid switch. This page is used to retrieve global settings information, such as icons for the buttons and the lid switch.

**Note**  
The preferred power button, sleep button, lid switch, and password-on-resume setting values are in effect only until the first time that the setting is changed. After that, all the power plans use the setting that the end user specifies.

 

When an end user clicks the battery meter, Windows displays two featured power-plan options. The default featured power plans are **Balanced** and **Power Saver**. If `PreferredPlan` is set to a different power plan, Windows displays **Balanced** and the specified plan.

Use the **powercfg -list** option to view the GUIDs for the different power plans on the Windows installation. For example:

```
C:\>powercfg -LIST

## Existing Power Schemes (* Active)

Power Scheme GUID: 381b4222-f694-41f0-9685-ff5bb260df2e  (Balanced)
Power Scheme GUID: 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c  (High performance)
Power Scheme GUID: a1841308-3541-4fab-bc81-f71556f20b4a  (Power saver) *
```

For more information, see the **powercfg** command-line Help and the topic: [How to Set the Default Power Plan](http://go.microsoft.com/fwlink/?LinkId=268347).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>GUID</em></p></td>
<td><p>Specifies a valid power-plan GUID. For example, <strong>381b4222-f694-41f0-9685-ff5bb260df2e</strong>. The default GUID is the Windows Automatic power plan.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[Microsoft-Windows-powercpl](microsoft-windows-powercpl.md) | **PreferredPlan**

## Valid Configuration Passes


generalize

specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-powercpl](microsoft-windows-powercpl.md).

## XML Example


The following XML output shows how to configure a GUID for `PreferredPlan`.

```
<PreferredPlan>381b4222-f694-41f0-9685-ff5bb260df2e</PreferredPlan>
```

## Related topics


[Microsoft-Windows-stobject](microsoft-windows-stobject.md)

[Microsoft-Windows-powercpl](microsoft-windows-powercpl.md)

 

 







