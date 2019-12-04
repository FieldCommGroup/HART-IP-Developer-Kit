
<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/FCG_logo_horizontal_color_lg600px.png" width=30% Align=right>

# README

## HART-IP Developer Kit

### Introduction

HART-IP enabled products have been available since 2009. To date the cast majority of products have been remote I/O. This includes WirelessHART Gateways, HART 4-20ma I/O, and Remote Terminals Units \(RTUs\).

The HART-IP Developer Kit provides a complete working demonstration of a HART-IP field device. Field Devices have long been supported by the HART-IP but are just now gaining interest in the HART community and industry. This kit provides a complete working HART-IP based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform.

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/IMG_1950-cropped-1.png" width=50% Align=right>


The two software modules are the:
* [**HART-IP Server \(hipserver\)**](https://github.com/FieldCommGroup/hipserver)  The hipserver component is essentially a HART-IP communication stack. It takes care of all HART-IP specific functions plus manages client subscriptions. The client subscriptions allow the hipserver to push the process and status data to client applications.
* [**Flow Device Application \(hipflowapp\)**](https://github.com/FieldCommGroup/hipflowapp)  The hipflowapp implements a complete flowmeter. The HART-IP Developer kit includes an ADC/DAC board that provides the physical connection for the hipflowapp. Since the HART Application Layer is independent of the underlying communication media this also provides an example of a complete HART-enabled field device.

These two software modules target operation under Ubuntu Linux and are each found in their own repository \([hipserver](https://github.com/FieldCommGroup/hipserver) and [hipflowapp](https://github.com/FieldCommGroup/hipflowapp)\).

This kit provides a simple way to evaluate HART-IP operation and learn the details needed to implement it in a field device \(or even an I/O\).

### About this repository

This repository serves provides the core documentation and instructions for the HART-IP Developer Kit. This includes directions for purchasing and assembling the kit, instructions for installing and operating the HART-IP FlowDevice, and specifications for the HART-IP FlowDevice itself. Links are provided to companion repositories including the [hipserver](https://github.com/FieldCommGroup/hipserver), [hipflowapp](https://github.com/FieldCommGroup/hipflowapp) and the [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient). The Windows HART-IP Client is a simple host application that can be used to communicate with and operate the HART-IP FlowDevice.

### Getting Started
There are two approaches to getting started with the HART-IP Developer Kit: buy a completed system from FieldComm Group or build you own using the documentation and software in these repositories. 

#### Getting a complete HART-IP Developer Kit from FieldComm Group
For convenience an assembled and complete HART–IP Developer Kit is available from FieldComm Group.  This kit provides a complete working HART-IP based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform, a HART-IP Server and a sample FlowDevice Application.  The FlowDevice EDD Source Code and documentation are included with this kit. 

Features include:
* Pre-Configured micro SD card containing the HART-IP Server and Flow Device Application running on UbuntuMATE (64-bit).
* Complete set of hardware including Raspberry Pi 3B+, DSLRKIT Power Over Ethernet PoE HAT, Waveshare Raspberry Pi High-Precision AD/DA together mounted on a DINrPlate DIN Rail Mount for Raspberry Pi 3.
* *Flow Device Developer Guide* Documentation
* HART-IP FlowDevice EDD Source Code, and 
* Four (4) hours Technical Support to help you get started.

Contact [FieldComm Group](https://www.fieldcommgroup.org/contact) for more information.

#### Building the HART-IP Developer Kit Yourself.

Alternatively, you can build your own system using the documentation and software from these repositories. Follow the instructions in these guides to build and operate your device:

1. [Read the FlowDevice Specification](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/hart-ip-flowdevice-spec.md)
2. [Purchase your parts using the Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/bill-of-materials.md)
3. [Install an operating system on your Pi Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md)
4. [Configure the FlowDevice software on the Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md)
5. [Operate the FlowDevice](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md)
6. [Connect a client to the device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/connect-a-client.md)



### **Version 1.0.0**

Initial release

* Raspberry Pi 3B+
* Waveshare Raspberry Pi High-Precision AD/DA
* UbuntuMATE 18.04 LTS 64-bit
* hipflowapp 1.0
* hipserver 3.6.1

