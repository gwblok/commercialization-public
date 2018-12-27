---
title: Cellular data connection icon
description: The one-, two-, or three-character codes used to signify the data connection type in the status bar can be modified.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: eec95772-cf38-4ded-b5c5-eede2e485a56


ms.date: 05/02/2017
ms.topic: article


---

# Cellular data connection icon


The one-, two-, or three-character codes used to signify the data connection type in the status bar can be modified. The default values are G (GPRS), 1x (RTT), DO (EVDO), E (EDGE), 3G (3G), H (HSDPA/HSUPA), LTE (LTE), or no letters displayed if there is no active connection.

**Limitations and restrictions**:

-   Partners cannot modify the types of data connections available; only the display code can be modified.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DataConnectionIcon"  
                         Description="Use to modify the one-, two-, or three-character codes used to signify the data connection type in the status bar."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Shell/SystemTray/DataConnectionStrings">  
          <Setting Name="1XRTTDEFAULT" Value="1X" />  
          <Setting Name="1XRTT" Value="1X" />  
          <Setting Name="EVDODEFAULT" Value="DO" />  
          <Setting Name="EVDOREV0" Value="DO" />  
          <Setting Name="EVDOREVA" Value="DO" />  
          <Setting Name="EVDOREVB" Value="DO" />  
          <Setting Name="GSMDEFAULT" Value="G" />  
          <Setting Name="GSMGSM" Value="" />  
          <Setting Name="GSMGPRS" Value="G" />  
          <Setting Name="GSMEDGE" Value="E" />  
          <Setting Name="UMTSDEFAULT" Value="3G" />  
          <Setting Name="UMTSUMTS" Value="3G" />  
          <Setting Name="UMTSHSDPA" Value="H" />  
          <Setting Name="UMTSHSUPA" Value="H" />  
          <Setting Name="UMTSHSPAPLUS" Value="H+" />  
          <Setting Name="UMTSDCHSPAPLUS" Value="H+" />  
          <Setting Name="UMTSHSPAPLUS64QAM" Value="H+" />  
          <Setting Name="LTEDEFAULT" Value="LTE" />  
          <Setting Name="LTEFDD" Value="LTE" />  
          <Setting Name="LTETDD" Value="LTE" />  
          <Setting Name="TDSCDMADEFAULT" Value="T" />  
          <Setting Name="TDSCDMAUMTS" Value="T" />  
          <Setting Name="TDSCDMAHSDPA" Value="H" />  
          <Setting Name="TDSCDMAHSUPA" Value="H" />  
          <Setting Name="TDSCDMAHSPAPLUS" Value="H+" />  
          <Setting Name="TDSCDMADCHSPAPLUS" Value="H+" />  
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To change the default one-, two-, or three-character codes used to signify the data connection type in the status bar, modify the `Value` that corresponds to the setting you want to change.

    > [!NOTE]
    > All the `Value` attributes are the current default values for each data connection type. You can change these to something else. Maximum character length is 3 characters.

    The following table shows the settings you can modify and their default values.

    | Setting Name      | Default Value | Description                                  |
    |:------------------|:--------------|:---------------------------------------------|
    | 1XRTTDEFAULT      | 1X            | 1XRTT connection                             |
    | 1XRTT             | 1X            | 1XRTT                                        |
    | EVDODEFAULT       | DO            | EVDO connection                              |
    | EVDOREV0          | DO            | EVDO rev. 0                                  |
    | EVDOREVA          | DO            | EVDO rev. A                                  |
    | EVDOREVB          | DO            | EVDO rev. B                                  |
    | GSMDEFAULT        | G             | GSM connection                               |
    | GSMGSM            |               | No GSM connection                            |
    | GSMGPRS           | G             | GSM General Packet Radio Service             |
    | GSMEDGE           | E             | GSM Enhanced Data rates for Global Evolution |
    | UMTSDEFAULT       | 3G            | UMTS connection                              |
    | UMTSUMTS          | 3G            | UMTS                                         |
    | UMTSHSDPA         | H             | High Speed Downlink Packet Access            |
    | UMTSHSUPA         | H             | High Speed Uplink Packet Access              |
    | UMTSHSPAPLUS      | H+            | High Speed Packet Access “Plus”              |
    | UMTSDCHSPAPLUS    | H+            | Dual-carrier HSPA+                           |
    | UMTSHSPAPLUS64QAM | By default, the value inherited from UMTSDCHSPAPLUS. <br/><br/> To set a value different from the value for UMTSDCHSPAPLUS, you must set the value explicitly. | UMTS HSPA+ 64QAM (high order modulation) |
    | LTEDEFAULT        | LTE           | LTE connection                               |
    | LTEFDD            | LTE           | LTE Frequency Division Duplexing             |
    | LTETDD            | LTE           | LTE Time Division Duplexing                  |
    | TDSCDMADEFAULT    | T             | TD-SCDMA connection                          |
    | TDSCDMAUMTS       | T             | TD-SCDMA                                     |
    | TDSCDMAHSDPA      | H             | TD-SCDMA High Speed Downlink Packet Access   |
    | TDSCDMAHSUPA      | H             | TD-SCDMA High Speed Uplink Packet Access     |
    | TDSCDMAHSPAPLUS   | H+            | TD-SCDMA High Speed Packet Access “Plus”     |
    | TDSCDMADCHSPAPLUS | H+            | TD-SCDMA Dual-carrier HSPA+                  |

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image containing this customization to a phone that has a UICC.

2.  Verify that the one-, two-, or three-character code(s) you used for the cellular data connection type is displayed in the status bar at the top of the screen.

    You may have to tap the clock to make the status bar appear if it is hidden.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
