# HART-IP FlowDevice Spec

## **HART-IP FlowDevice**

This document supplies the Device-Specific Documentation for the HART-IP FlowDevice. It includes lists of the commands supported the engineering units supported, behavior of status, and interfaces to the FlowDevice

## Introduction

The HART-IP FlowDevice simulates a simple-minded Coriolis flow meter. The FlowDevice measures the mass flow and the drive current required maintain the vibration of the flow tube.

As is often the case, the Flow measurement supports accurate measurement across a 10:1 dynamic range \(24,000:2,400 kg/h\) or \(with reduced accuracy\) across a 100:1 turndown. At low flow status set and the flow is coerced to 0 kg/h.

The drive current generally increases in Coriolis meters as deposits build up in the flow tube. A high drive current value sets status indication recommending maintenance be performed on the meter \(clean the flow tube\).

The generation of status enables publishing by exception -- A feature available in all HART 7 devices. Status is specified in the _Status Information_ section.

The FlowDevice implements a HART 7 enabled HART-IP field device. In fact, FieldComm Group has performed standard compliance testing of the FlowDevice Application Layer to confirm conformance. The Application Layer is actually isolated and independent from HART-IP. This same Application Layer could provide a basis for HART 4-20mA or WirelessHART device

The Flow Device supports the minimal set of commands to demonstrate HART-IP capabilities including publishing \("burst-mode"\) runtime process and status data:

* Process data is published at up-to the 20 updates/sec required by HART-IP. All trigger modes \(e.g., continuous, windowed, level, etc.\) are supported.
* Device Status, Extended Device Status, Device Variable Status and Command 48 are all updated based on current device condition. For example, low flow will update the Device Variable Status and Device Status accordingly.
* Configuration changed counter is updated as the FlowDevice properties are modified.

Thus the HART-IP FlowDevice demonstrates the power of publishing by exception and Smart Data Publishing.

The Flow measurement can be reported in a variety of engineering units thus demonstrating another feature of the HART Protocol.

### Scope

This document provides a detailed description of the FlowDevice's features and operation. This document also identifies any tailoring of the HART Protocol by the FlowDevice \(e.g., the truncation of Comamnd 3\). The details included are sufficient to enable the FlowDevice use by generic HART-IP client applications.

### Who should use this document?

Device developers will find this document helpful as it provides a high-level overview. This overview could be helpful when a developer begins reviewing the HART-IP FlowDevice source code.

Users and Manufacturers that are trying to understand the possibilities offered by HART-IP may find this useful when setting up and benchmarking multiple devices. Operating multiple devices in the same network can be used to evaluate the responsiveness, latency and throughput of HART-IP networks.

### Abbreviations and definitions

PV : Primary Value

SV : Secondary Variable

TV : Tertiary Variable

QV : Quaternary Variable

### References

* HART Communication Protocol.  [FieldCommGroup](https://www.fieldcommgroup.org)
* Raspberry Pi 3B+ [https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)
* Waveshare High-Precision AD/DA Board. [https://www.waveshare.com/wiki/High-Precision\_AD/DA\_Board](https://www.waveshare.com/wiki/High-Precision_AD/DA_Board). 
* Windows HART-IP Client [https://github.com/FieldCommGroup/WindowsHartIpClient](https://github.com/FieldCommGroup/WindowsHartIpClient)
* ssh [Secure Shell](https://en.wikipedia.org/wiki/Secure_Shell)

## Device Identification

The following table summarizes the device identification data/codes returned by the **HART-IP FlowDevice**

|  |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- |
| Device | HART-IP FlowDevice |  | Device Type Code | 0xF9FD |
| Manufacturer | FieldComm Group |  | Manufacturer ID | 0x00F9 |
| Universal Rev. | 7 |  | Device Revision | 1 |
| Software Revision | 0x28 |  | Hardware Revision | 0x08 |
| PHY Sig Code | 6 |  | Device Profile | 65 / 0x41 |

## Product Overview

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/IMG_1950-cropped-1.png" width=60% align=right>

The **HART-IP FlowDevice** demonstrates operation of a field device communicating via HART-IP. The device is a fully functioning HART 7 device and supports mandatory HART-IP commands including publishing \(burst\) process data and status.

The **HART-IP FlowDevice** is designed to operate on a Raspberry Pi 3B+ using a Waveshare _Raspberry Pi High-Precision AD/DA Expansion Board_. The Waveshare board includes the ADC and DAC used as the "process interface" for the field device.

Currently only the ADC on the Waveshare board is used. AD0 measures the flow rate and AD1 measures the flow tube current. In the next Device Revision will support the Flow Device Family. In that Device Revision, DA0 is planned to be used to control a batching relay.

## Product Interfaces

The HART-IP FlowDevice operates on a Raspberry Pi 3B+ with a Waveshare ADC/DAC board. The Waveshare board provides the Process Interface.

The RaspBerry Pi itself has several interfaces that are possible to utilize. First, the Ethernet and WiFi interfaces support HART-IP as the primary client interface. Remote management is also possible via those channels. In addition, monitor, keyboard and mouse can be connected to the HDMI and USB interfaces respectively.

### Process Interface

Waveshare "High-Precision AD-DA" provides the Process interface.

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/Screen%20Shot%202019-10-07%20at%2012.05.34%20.png" width=70%>

Flow is measured via AD0 and normally controlled via the Trim Pot \(see item 8\). The Jumpers \(12\) connect the Trim Pot to AD0. If an external Flow is to be used then the AD0-ADJ jumper should be removed. External flow voltage would be connected at Terminals \(2\) AD0.

All ADCs accept single-ended analog value \(0-5Vdc\). See ADS1256 for ADC specifications at [http://www.ti.com/product/ADS1256](http://www.ti.com/product/ADS1256)

Likewise, Drive Current is measured via AD1 which is normally connected to the Photodetector \(6\). The Jumpers \(12\) connect the Photodetector to AD1. If an external Drive Current is to be used then the AD1-LDR jumper would be removed. External Drive Current would be connected at Terminals \(2\) AD1. Drive Current is reverse-acting. Full scale signal produces a low Drive Current. This is equivalent to normal operation with the Photodetector uncovered.

**Future Totalizer Function** The Relay is simulated using DAC0 \(9\) - Channel A of Texas Instruments DAC8552. Operation is binary with DAC set to zero or full scale. Jumpers \(13\) control whether DAC0 is connected to the LED or not. DAC0 may be connected to an external Relay to switch Flow off and on to simulate batching cycles. See DAC8552 for output specifications at [http://www.ti.com/product/DAC8552](http://www.ti.com/product/DAC8552).

For more information see the Waveshare documentation at [https://www.waveshare.com/wiki/High-Precision\_AD/DA\_Board](https://www.waveshare.com/wiki/High-Precision_AD/DA_Board).

### Host interface

The principal Host Interface is HART-IP. This provides both publish by exception and request/response services to access the HART-IP FlowDevice. HART-IP is supported by a wide-range of client applications including data-historians, plant asset management, and many cloud-based applications.

Evaluation of the FlowDevice can be quickly undertaken using the [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient). This allows low cost evaluation of HART-IP using low-cost Raspberry Pi hardware and open source software.

The Raspberry Pi 3B+ also supports Ubuntu operating system with access via [ssh](https://en.wikipedia.org/wiki/Secure_Shell) or with a monitor/keyboard/mouse.

### Local Interfaces, Jumpers And Switches

#### Raspberry Pi 3B+

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/Raspberry%20Pi%203%20B%2B%20Diagram.r1.png" width=75%>

There are no jumpers on the Raspberry Pi 3B+. However, the Raspberry Pi 3B+ has a number of connectors. The following are of interest:

* **Micro SD Card Slot** must have SD Card "hard drive" installed.  this contains the operating system, FlowDevice application, etc.
* **Micro USB Port** normally supplies power to the system.  If your system includes the Power-Over-Ethernet \(POE\) daughter card then this connector will be empty
* **GPIO Header** provides expansion for adding I/O cards, etc.  the Waveshare ADC/DAC card mounts here \(along with the Power-Over-Ethernet adapter if it is used\)
* **Gigabit Ethernet Port**  When wired Ethernet \(including POE\) is used the CAT5 or Cat6 cable will be plugged in here.  There will be no connection if Wifi is used.
* **HDMI Port** If you want a local monitor and keyboard, the monitor will plug in here
* **USB Ports** can be used to connect a keyboard and mouse.

Note: Often the system can be controlled remotely using \(for example\) ssh. In this case no keyboard, mouse, monitor are needed.

#### WaveShare PCB

There are jumpers on the [WaveShare PCB](file://localhost/Users/wallyp/Desktop/Screen%20Shot%202019-10-07%20at%2012.05.34%20.png) that control whether the onboard circuits source the "process interface" or not \(item 12\).

The [WaveShare PCB](file://localhost/Users/wallyp/Desktop/Screen%20Shot%202019-10-07%20at%2012.05.34%20.png) jumpers at item 14 should be set to +5VDC.

For more information see _**Process Interface**_ section above.

## Device Variables

### \[0\] Mass Flow \(Pot\)

Returned as PV in Command 3. The following Engineering units from Common Table 2.72. are supported:

| Code |  | Units | Description |
| :--- | :--- | :--- | :--- |
| 74 |  | kg/min | kilograms per minute |
| 75 |  | kg/h | kilograms per hour |
| 81 |  | lb/min | pounds per minute |
| 82 |  | lb/h | pounds per hour |
| 84 |  | ton/min | short tons \(i.e., 2000 lbs\) per minute |
| 85 |  | ton/h | short tons per hour |

The FlowDevice defaults to to kg/h

**Limits and Accuracy** Transducer limits are 0/24,000 kg/h. The Nominal flow range is 2,400/24,000 kg/hr. The maximum extended flow range is 240/24,000 kg/hr \(with loss in accuracy below 2,400 kg/hr\). Below nominal flow rate Device Variable Status is set accordingly.

Note: Flow meters have about 10:1 turndown. For flows in the range 240-2400 the meter still works. - Just not so accurate.

#### Status

Set Device Variable Status to “Poor Accuracy” \(top 2 MSBits = 01\) when low flow \(&lt;2,400 kg/hr\)

If flow &lt; 240 kg/h the flow is coerced to 0. set “PV out of limits” in device status byte.

### \[1\] Drive Current \(photo-resistor\)

Returned as SV in Command 3

Dark means more current. Engineering units invariant as mA. Transducer limits of 0/150mA. Alarm at current above 60mA

Normal value \(e.g., 10mA\) when photo resistor light is bright. 150mA when totally dark \(e.g., thumb over it\).

#### Status

Non-PV Out of limits set when drive current &gt; 150mA.

### \[2\] Total \(Future - Addition in Device Revision 2\)

Returned as TV in Command 3

This is the integration of the flow into a total. This is implemented per the Totalizer Device Family Spec.

DAC0 \(DAC8552 - U1\) is used to as the coil driver for the relay function from the Totalizer Device Family. Full scale output from the DAC is produced when relay energized.

Totalizer shall be preset using Command 79.

### \[244-249\] Standard Device Variables

Standard Device Variables 245, 249 return HART NaN

## Dynamic Variables

PV is fixed to "Flow" \(Device Variable 0\) ; SV to "Drive Current" \(Device Variable 1\)

## Status Information

### Device Status

“PV out of limits” set when Flow &lt; 240

"Non-PV Out of limits" set when Drive Current &gt;= 150mA

### Extended Device Status

“Device Needs Maintenance” set when Drive Current goes hi.

### Additional Device Status \(Command \#48\)

Need to assign some bits in byte 0 of Command 48 for status purposes. e.g., low flow; hi drive current; — anything else easy/interesting?

_begin SJVr notes..._

Command 48 Byte 0

* Upper nibble is Secondary status
* Lower nibble is Primary status

Byte 0 status is bit mapped

| Bit | Description | Range |
| :--- | :--- | :--- |
| 0x08 | Hi bit is Over Range | value is &gt;= USL |
| 0x04 | High Alarm | value &gt;= high alarm |
| 0x02 | Low Alarm | value is &lt;= low alarm |
| 0x01 | Lo bit is Under Range    value is &lt;= LSL |  |

Byte 1 thru 5 are always zero

Byte 6 is Extended Field Device Status – none of these bits are currently supported.

| Code | Map | Description |
| :--- | :--- | :--- |
| 0x01 | N3,4 | **Maintenance Required** \[Condensed Status\] This bit is set to indicate that, while the device has not malfunctioned, the Field Device requires maintenance. Devices supporting this bit should support the Condensed Status Commands \(see Common Practice Command Specification\). |
| 0x02 | S, N5 | **Device Variable Alert** This bit is set if any Device Variable is in an Alarm or Warning State. The host should identify the Device Variable\(s\) causing this to be set using the Device Variable Status indicators. |

## Universal Commands

The HART-IP FlowDevice is HART 7 compliant and supports all the specified Universal Commands. Notes on Universal Commands Include

* Command 2: Read Loop Current And Percent Of Range\

  Loop Current returns HART NaN \(there is no loop current\)

* Command 3 Read Dynamic Variables And Loop Current\

  Truncated to only PV, SV

* Command 9 Read Device Variables with Status\

  Truncated to 4 Device Variables

* Command 48 Read Additional Device Status\

  Truncated after "Standardized Status 1"

## Common-Practice Commands

The HART-IP FlowDevice is HART-IP compliant and, consequently, supported burst-mode.

### Supported Commands

The following Common Practice commands are supported

* Command 35 Write Primary Variable Range Values
* Command 53 Write Device Variable Units\
* Command 54 Read Device Variable Information\
* Command 79 Write Device Variable
* Command 95 Read Device Communications Statistics
* Command 103 Write Burst Period
* Command 104 Write Burst Trigger
* Command 105 Read Burst Mode Configuration\
* Command 107 Write Burst Device Variables
* Command 108 Write Burst Mode Command Number
* Command 109 Burst Mode Control
* Command 532 Read Client Subscription Summary
* Command 533 Write Client Subscription Flags
* Command 534 Read Device Variable Command Code

### Burst Mode

Supported. Publish up to 20 updates/second per HART-IP requirements.

## Device-Specific Commands

None

## Performance

### Sampling Rates

### Command Response Times

Command Response Times are typically under 5ms.

### Busy and Delayed-Response

Busy and Delayed Response never happen.

## Annex A. Revision History

