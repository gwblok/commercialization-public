---
title: HMD Exerciser Kit Software

description: The HMD Exerciser Kit automates validation of mixed reality (MR) head mounted displays (HMDs) and PCs.
keywords:
- HMD, testing
- head mounted display, testing
- HDMI USB testing 

ms.date: 1/10/2018
ms.topic: article


---

# HMD Exerciser Kit Software

The HMD Exerciser Kit includes the following tools:

| **Tool**                          | **Description**                   |
-----------------------------------|-----------------------------------
| ConnExUtil.exe                    | Command line tool for exercising HMD Exerciser features
| HmdKit.cs                         | C\# class that can be used to talk to the HMD Exerciser  from PowerShell or managed test applications 

## ConnExUtil.exe

ConnExUtil.exe is the command line tool for the HMD Exerciser. The tool is installed as part of the MUTT Software Package. Download it [here](https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/mutt-software-package)

Supported command line options are described in the following table.


> [!div class="mx-tdCol3BreakAll"]
> 
> | **Use case**         | **Option**           | **Description**      |
> -----------------------|----------------------|----------------------
> | Device Discovery. <br/> List all devices connected to MUTT ConnEx-C. | **/list**            | For USB connected devices, this option lists the device instance path. For audio connected devices it shows **Audio**. To view audio devices, use this in combination with the **/all** parameter. Lists with 1-based index that can be used for input to the **/\#** parameter.
> | Device Selection. <br/> Select all devices connected to MUTT ConnEx-C, including audio.   | **/all**            | Optional.<br/>Without this parameter, the utility addresses USB connected devices. Use this parameter only if an audio connected device is in use. Audio discovery is time consuming and disabled by default.|
> | Device Selection.<br/>Select a specific device connected to MUTT ConnEx-C 'n'.   | **/\#** *n* | Optional.<br/>Input *n* is a 1-based index of the available devices connected to MUTT ConnEx-C which can be viewed by using the **/list** parameter. Without this parameter, the default behavior is to run each command on all MUTT ConnEx-C boards.              |
> | Set the USB port connected to **J1** | **/setPort** *p*     | Switches to the  specified port, *p*. <br/>Connect a port either by specifying number (1-4) or by name (**J2**, **J3**, **J4**, **J6**). <br/>0 disconnects all ports.|
> | Get the current USB Port connected to **J1** | **/getPort** | Reads the currently connected port. <br/>Reads a port either by specifying number (1-4) or by name (**J2**, **J3**, **J4**, **J6**).<br/>0 disconnects all ports.|
> | Set the HDMI port connected to **J1**  | **/setHdmiPort** *p* | Switches to the specified port *p*.<br/>Connects a port either by specifying number (1-2) or by name (**J2**, **J3**).<br/>0 disconnects all ports.|
> | Get the current HDMI port connected to **J1**| **/getHdmiPort**     | Reads the currently connected port.<br/>Reads a port either by specifying number (1-2) or by name (**J2**, **J3**).<br/>0 disconnects all ports.|
> | Read amperage/volt information  | **/volts**<br/>**/amps**<br/>**/version**| Reads the current  voltage.<br/>Reads the current amperage.<br/>Reads the device version.|
> | Select the HMD port of interest    | **/SetHmd** *p*   | Select the HMD port of interest to the HMD on port p.|
> | Get the current brightness of a display    | **/DisplayBrightness** *p*| Gets the brightness of display p.|
> | Get the color of a display    | **/DisplayColor** *p*   | Get the color of display p.|
> | Get the current RMS volume from HMD | **/GetVolumeRms** | Gets the current RMS volume from the headset.|
> | Get the peak volume from HMD | **/GetVolumePeak**   | Gets the peak volume detected during the sample window.|
> | Get the average volume from HMD | **/GetVolumeAvg** | Gets the average volume from the HMD over the sample window.|
> | Set the number of audio samples to take  | **/SetVolumeSampleCount** *p*| Sets the number of samples, p, to collect before the /GetVolume commands return.|
> | Set the angle of the specified servo  | **/SetServoAngle** *p* *q*| Sets the angle of servo *p* to *q* degrees.|
> | Enable SuperSpeed    | **/SuperSpeedOn**    | Enables SuperSpeed globally for current and future connections until a **/SuperSpeedOff** command is sent.<br/>SuperSpeed is enabled by default.<br/>If SuperSpeed is disabled, and port 1 or 2 is connected, this command triggers a reconnect at SuperSpeed.|
> | Disable SuperSpeed   | **/SuperSpeedOff**  | Disables SuperSpeed globally for current and future connections until a **/SuperSpeedOn**  command is sent or the device is reset.<br/>If SuperSpeed is enabled and port 1 or 2 is connected, this command triggers a reconnect with SuperSpeed lines disabled.|
> | Set command delay    | **/setDelay** *t*    | Sets command delay *t* in seconds.<br/>Setting a command delay will cause the next **/setPort** or **/SuperSpeed{On/Off}** command to be delayed by *t* seconds where **t** ranges from 0 to 99.<br/>This is a one-time setting, only the next command is delayed. Sending multiple commands before the delay timer has expired is not supported.|
> | Set disconnect timeout in milliseconds     | **/setDisconnectTimeout** *t*| Sets a disconnect timeout for the next non-zero **/setPort** command. On the next connect event, the port will only remain connected for *t* milliseconds before disconnecting. This is a one-time setting, only the next connect event will be automatically disconnected.<br/>Allowed range is from 0 to 9999 ms.|
> | Batch Command:<br/>Output power measurements to a .csv file. | **/powercsv** | Appends the current power measurements and timestamp into power.csv The first run creates power.csv. On subsequent runs appends data to this file.<br/>Rename or delete the file to start fresh data capture. Each run appends a line with the following format: *\<index\>,\<time\>, \<volts\>,\<amps\>*.<br/>*index* is the device index given by **/list**, so multiple devices may be monitored simultaneously.<br/>*time* is the raw timestamp in seconds.<br/>*volts* and *amps* are recorded to two decimal places.<br/>This data may be captured over long periods of time and plotted in a spreadsheet application, see the cxpower.cmd script.|
> | Batch Command:<br/>Run unit test of major functionality | **/test** | Tests all the major functionality of the device. Use for basic validation of the functionality of the device. If this command fails, please power cycle the device and update the firmware. |
> | Batch Command:<br/>Basic demo of the port switching sequence. | **/demo** *d* | Loops through all ports one time, with *d* second delay on each port.<br/>Writes the port number, volts and amps on each port into demoresult.txt. |


## HmdKit.cs

Download the HmdKit.cs code from https://github.com/Microsoft/busiotools/tree/master/hmdvalidationkit

### Usage

- Include HmdKit.cs in your automation app.
- Create an instance of the HmdKit class and call findHmdKitDevice to scan COM ports for HmdKits. 
- Check the return value of findHmdKitDevice or the IsPresent property.
- Use the methods to perform actions like connecting USB/HDMI or checking display brightness. 
- If a method returns false, the device may be in a bad state or the COM port may be in use by another application.

### Classes
```public class HmdKit : IDisposable``` <br>
This class provides managed access to the functionality of the HMD Validation Kit.

### Private Members
```private const int HmdKitBaudRate = 9600;```<br>The default baud rate for the HMD Kit's Serial over USB communication is 9600 baud.

```private const int RetryCount = 3;```<br>
This constant controls the number of retries for sending a command.

```private const string HmdKitVersion = "01";```<br>
 This is the string hardcoded in the HMD Validation Kit for the version. This constant should match the expected version from the HMD Validation Kit.

```private const string HmdKitShieldType = "08";```<br>
This specifies the type of shield detected by the HMD Validation Kit. The current revision should always detect shield type "8".

```private const int ResponseTimeDefault = 500;```<br>
 This is the default response time that should provide enough time for a simple command to complete. Use this for commands that don't involve waiting for something to happen on the HMD Validation Kit like taking audio samples or waiting for sensor data.

```private const int ResponseTimeColorSensor = 2000;```<br>
 This time should provide enough window for the TCS color sensor's "integration time" to elapse and for the HMD Validation Kit to return a value. See the TCS34725 documentation for more information.

```private int responseTimeGetVolume = 1000;```<br>
This is a non-constant value that should provide enough time for a "GetVolume*" command to run for the specified number of samples. It will change every time the SetVolumeSampleCount method is used.

```private SerialPort serialPort;```<br>
 This is the internal instance of the serial port attached to the HMD Validation Kit.

```private Dictionary<string, string> hmdKitCommand = new Dictionary<string, string>();```<br>
This dictionary translates the friendly names of the commands to their real command strings that will be sent over the cable to the HMD Validation Kit.

```private object hmdKitLock = new object();```<br>
This lock is set when the HMD Validation Kit's serial port is being accessed.

```private bool isPresent;```<br>
This private member tracks the enumeration state of the HMD Validation Kit.

### Constructors:
```public HmdKit()```<br>
Initializes a new instance of the HmdKit class. This maps all of the appropriate friendly names to their serial commands along with initializing the enumeration state to false.

### Properties:

```public bool IsPresent```<br>
Gets a value indicating whether the HMD Validation Kit is enumerated.

### Methods:

```public void Dispose()```<br>
Implementation of the Dispose interface to dispose of the managed resources used by the HmdKit class.

```public bool FindHmdKitDevice()```<br>
Checks all open serial ports for HMD Exercisers. Returns true if a valid HMD Kit is detected, otherwise returns false.

```public void SendCommand(string command, int responseTime, string parameter, out string output)```<br>
Sends a command to the HMD Exerciser. The command should return within ```responseTime``` milliseconds. 
- ```command``` - The command to send to the HMD Kit. The command should be a part of the hmdKitCommand Dictionary.
- ```responseTime``` - The time that the SendCommand method should wait for a response. This can be longer for commands that will take more time.
- ```parameter``` - A parameter for commands that set USB ports, HDMI ports, etc. This will be appended to the command and sent to the HMD Kit.
- ```output``` - Returns with the response for commands that need to get information from the HMD Kit

```public void SendCommand(string command, int responseTime, string parameter = null)```<br>
 Sends a command to the HMD Exerciser. The command should return within responseTime milliseconds. This overload doesn't have an output and the parameter is optional. 
- ```command``` - The command to send to the HMD Kit. The command should be a part of the hmdKitCommand Dictionary.
- ```responseTime``` - The time that the SendCommand method should wait for a response. This can be longer for commands that will take more time.
- ```parameter``` -  An optional parameter for commands that set USB ports, HDMI ports, etc. This will be appended to the command and sent to the HMD Kit.

```public void SetUsbPort(string port)```<br>
Sets the USB port that is connected to J1. 
- ```port``` - Ports can be either 0,1,2,3,4 or go by the silkscreen on the PCB: J2,J3,J4, or J6. The mapping is J2=1 J3=2 J4=4 J6=3

```public string GetUsbPort()```<br>
Gets the currently connected USB port on the HMD Exerciser.Returns the currently connected USB port. '0' designates no port is connected.

```public void SetHdmiPort(string port)```<br>
Sets the currently connected HDMI port. 
- ```port``` - The port to connect. Valid values are J2/J3 or 1/2. J2 and 1 are equivalent and J3 and 2 are equivalent.

```public string GetHdmiPort()```<br>Gets the index of the currently connected HDMI port from the HMD Exerciser. Returns the currently connected HDMI port. '0' means no port is connected. Otherwise, the port will be 2(J2) or 1(J3)

```public void SetServoAngle(string servo, string degrees)```<br>
Sets the angle of the specified servo in degrees. 
- ```servo``` - The servo to set the angle on. See the silkscreen on the servo connectors of the HMD Exerciser.
    - 1 Selects "Servo 1"
    - 2 Selects "Servo 2"
- ```degrees``` - The degree position to move to in the servo's sweep. The degrees should be between 45* and 135* for most servos.

```public void SetPresence(bool userPresent)```<br>
Sets the presence spoofing LED to either drown out the HMD's presence sensor with light (no user presence) or spoof user presence. 
- ```userPresent``` - The desired user presence state
    - ```true``` - User presence is spoofed by imitating the IR presence sensor response pattern.
    - ```false``` - User presence is "removed" by flooding the IR presence sensor with IR light, removing the ability for it to see the reflection of the response pattern.

```public string GetDisplayBrightness(int display)```<br>
Gets the brightness of the requested display using the TCS34725 color sensors on the HMD Board.
   >[!NOTE] 
   > This is also affected by the HMD that is set. See ```SetHmd``` for more info.

Returns the raw display brightness from the indicated display. The brightness is a magnitude between 0 and 65535. See the TCS34725 color sensor docs for more information. 
- ```display``` - The display to read color from.
    - ```0``` - The left display from the perspective of wearing the HMD
    - ```1``` -  The right display from the perspective of wearing the HMD

```public void GetDisplayColor(int display, out string red, out string green, out string blue)```<br>
 Gets the RGB color values for the specified display. The colors are a magnitude between 0 and 65535. See the TCS34725 color sensor docs for more information. 
- ```display``` - The display to read color from.
    - ```0``` - The left display from the perspective of wearing the HMD
    - ```1``` -  The right display from the perspective of wearing the HMD
- ```red``` - Out param that returns the magnitude of the red component of the received light.
- ```green``` - Out param that returns the magnitude of the green component of the received light.
- ```blue``` - Out param that returns the magnitude of the blue component of the received light.

```public void SetVolumeSampleCount(string samples)```<br>
Sets the number of volume samples to take before returning a result from any of the getVolume* methods. The default value is 2048 and the max is ULONG_MAX. THe sample rate of the Arduino is set to 38.4kHz. 
- ```samples``` - The number of samples to collect before returning a volume level. One second is approximately 40,960 samples.

```public string GetVolumeRms()```<br>
Gets the RMS volume level on the 1/8" jack of the HMD exerciser over a number of samples. The result will be between 0 and 100\*sqrt(2). The number of samples can be configured using ```setVolumeSampleCount```.
Volume levels are amplified on the PCB to give a full range response (0-5V) over headphone level signals. The center level is 2.5V.
Returns the RMS volume over the given sample period on a scale of 0-100*sqrt(2), since the volume is not centered on zero.

```public string GetVolumePeak()```<br>
 Gets the peak volume level on the 1/8" jack of the HMD exerciser over a number of samples. The number of samples can be configured using ```setVolumeSampleCount```.
Volume levels are amplified on the PCB to give a full range response (0-5V) over headphone level signals. The center level is 2.5V.
Returns the highest sample over the given sample period on a scale of 0-100.

```public string GetVolumeAvg()```<br>
Gets the average volume level on the 1/8" jack of the HMD exerciser over a number of samples. The number of samples can be configured using ```setVolumeSampleCount```.
Volume levels are amplified on the PCB to give a full range response (0-5V) over headphone level signals. The center level is 2.5V.
Returns the average volume over the given sample period on a scale of 0-100.

```public void SetHmd(int hmd)```<br>
Sets the HMD port that the other methods will act on. If the HMD of interest is plugged into P1, set the HMD to 1. if the HMD of interest is lugged into P2, set the HMD to 2. 
- ```hmd``` -  The HMD you would like brightness, presence, and color commands to apply to.
    - ```1``` - The HMD attached to port P1
    - ```2``` - The HMD attached to port P2

```public string Volts()```<br>
Gets the VBus voltage from the USB port. Returns the USB voltage as displayed on the LCD

```public string Amps()```<br>
 Gets the current drawn by the currently selected USB port. Returns the current as displayed on the LCD.

```public void SuperSpeed(bool status)```<br>
Sets the superspeed ports on or off. Pass true to enable superspeed lines and false to disable superspeed lines. 
-  ```status``` -  The desired status of the SuperSpeed lines. 
    - ```True``` - Connected
    - ```False``` - Disconnected

```public void CommandDelay(int delay)```<br>
 Sets a delay in seconds before the next issued command will execute. 
- ```delay``` -  The delay in seconds before the next command sent to the HMD kit will execute.

```public void DisconnectTimeout(int timeout)```<br>
 Sets a timeout for the port to disconnect after the next connect command is sent. 
- ```timeout``` -  The time in milliseconds the port will wait to disconnect after the next connect command is sent.

```protected virtual void Dispose(bool disposing)```<br>
Implementation of the Dispose interface to dispose of the managed resources used by the HmdKit class. 
-  ```disposing``` - If true, the managed resources are disposed.


## Software Examples

### ConnExUtil 

#### Connect to an HMD on HDMI/USB port J2
```
connexutil.exe /SetPort 1
connexutil.exe /SetHDMIPort 1
```

Alternatively, use the port name as printed on the board:
```
connexutil.exe /SetPort J2
connexutil.exe /SetHDMIPort J2 
```

#### Disconnect all HDMI/USB Ports
```
connexutil.exe /SetPort 0
connexutil.exe /SetHDMIPort 0
```

#### Select the HMD attached to port P1
```
connexutil.exe /SetHmd 1
```

#### Get brightness of each display
```
connexutil.exe /DisplayBrightness 0
connexutil.exe /DisplayBrightness 1
```
### HmdKit.cs
```cs
HmdKit kit = new HmdKit();
kit.FindHmdKitDevice();
if(kit.IsPresent)
{
Console.WriteLine("Found HMD Kit");
for(int i = 0; i <= 4; i++)
{
        kit.SetUsbPort(i.ToString());
        if(i < 3)
        {
        kit.SetHdmiPort(i.ToString());
        }
}
kit.SetHdmiPort("1");
kit.SetUsbPort("1");
kit.SetPresence(true);
kit.SetServoAngle("1", "90");
kit.SetVolumeSampleCount("2048");
kit.SuperSpeed(true);

String r, g, b = "";
Console.WriteLine("\nSelecting HMD 1");
kit.SetHmd(1);
Console.WriteLine("Display 0 brightness: " + kit.GetDisplayBrightness(0));
kit.GetDisplayColor(0, out r, out g, out b);
Console.WriteLine("Display 0 red:" + r + " green:" + g + " blue:" + b);
Console.WriteLine("Display 1 brightness: " + kit.GetDisplayBrightness(1));
kit.GetDisplayColor(1, out r, out g, out b);
Console.WriteLine("Display 1 red:" + r + " green:" + g + " blue:" + b);

Console.WriteLine("\nSelecting HMD 2");
kit.SetHmd(2);
Console.WriteLine("Display 0 brightness: " + kit.GetDisplayBrightness(0));
kit.GetDisplayColor(0, out r, out g, out b);
Console.WriteLine("Display 0 red:" + r + " green:" + g + " blue:" + b);
Console.WriteLine("Display 1 brightness: " + kit.GetDisplayBrightness(1));
kit.GetDisplayColor(1, out r, out g, out b);
Console.WriteLine("Display 1 red:" + r + " green:" + g + " blue:" + b);
Console.WriteLine("Press any key to exit...");
Console.ReadKey();
}
```