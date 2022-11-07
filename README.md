
<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/FCG_logo_horizontal_color_lg600px.png" width=30% Align=right>

# README

## HART-IP Developer Kit 1.2

### Introduction

HART-IP enabled products have been available since 2009. To date the majority of products have been remote I/O. This includes WirelessHART Gateways, HART 4-20ma I/O, and Remote Terminals Units \(RTUs\).

The HART-IP Developer Kit provides a complete working demonstration of a HART-IP field device. Field Devices have long been supported by HART-IP but are just now gaining interest in the HART community and industry. This kit provides a complete working HART-IP 2.0 based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform.

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/IMG_1950-cropped-1.png" width=50% Align=right>


The two software modules are the:
* [**HART-IP Server \(hipserver\)**](https://github.com/FieldCommGroup/hipserver)  The hipserver component is essentially a HART-IP communication stack. It takes care of all HART-IP specific functions plus manages client subscriptions. The client subscriptions allow the hipserver to push the process and status data to client applications.  \
	New for version 1.2:
	* HART-IP versions 1 and 2
	* Secured connections with TLS/PSK or SRP and DTLS/PSK or SRP
	* A security Key Management Service
	* Syslogging
	* Audit Logging
	* Direct messages
	* < more here >
	
* [**Flow Device Application \(hipflowapp\)**](https://github.com/FieldCommGroup/hipflowapp)  The hipflowapp implements a complete flowmeter. The HART-IP Developer kit includes an ADC/DAC board that provides the physical connection for the hipflowapp. Since the HART Application Layer is independent of the underlying communication media this also provides an example of a complete HART-enabled field device.

These two software modules target operation under Ubuntu Linux and are each found in their own repository \([hipserver](https://github.com/FieldCommGroup/hipserver) and [hipflowapp](https://github.com/FieldCommGroup/hipflowapp)\).

This kit provides a simple way to evaluate HART-IP operation and learn the details needed to implement it in a field device \(or even an I/O\).

### About this repository

This repository provides the core documentation and instructions for the HART-IP Developer Kit. This includes directions for purchasing and assembling the kit, instructions for installing and operating the HART-IP FlowDevice, and specifications for the HART-IP FlowDevice itself. Links are provided to companion repositories including the [hipserver](https://github.com/FieldCommGroup/hipserver), [hipflowapp](https://github.com/FieldCommGroup/hipflowapp) and the [Portable HART-IP Client](https://github.com/FieldCommGroup/Portable-HART-IP-Client). The Portable HART-IP Client is a web host application that can be used on Linux, Windows and MacOS to communicate with and operate the HART-IP FlowDevice.

### Getting Started
There are two approaches to getting started with the HART-IP Developer Kit: buy a completed system from FieldComm Group or build you own using the documentation and software in these repositories. The paid kit for version 2 will be released at a later date.

#### Get a complete HART-IP Developer Kit from FieldComm Group
For convenience, an assembled and complete HART–IP Developer Kit is available from FieldComm Group.  This kit provides a complete working HART-IP based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform: a HART-IP Server and a sample FlowDevice Application.  The FlowDevice EDD Source Code and documentation are included with this kit. 

Features include:
* Pre-Configured micro SD card containing the HART-IP Server and Flow Device Application running on UbuntuMATE (64-bit).
* Complete set of hardware including Raspberry Pi 3B+, DSLRKIT Power Over Ethernet PoE HAT, Waveshare Raspberry Pi High-Precision AD/DA together mounted on a DINrPlate DIN Rail Mount for Raspberry Pi 3.
* *Flow Device Developer Guide* Documentation
* HART-IP FlowDevice EDD Source Code, and 
* Four (4) hours Technical Support to help you get started.

Note: Version 2 of this kit will be released later in 2023.

Contact [FieldComm Group](https://www.fieldcommgroup.org/contact) for more information.

#### Build the HART-IP Developer Kit Yourself

Alternatively, you can build your own system using the documentation and software from these repositories. Follow the instructions in these guides to build and operate your device:

1. [Read the FlowDevice Specification](doc/hart-ip-flowdevice-spec.md)
2. [Purchase your parts using the Bill of Materials](doc/bill-of-materials.md)
3. [Install an operating system on your Pi Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md)
4. [Configure the FlowDevice software on the Pi](doc/configure-the-flow-device.md)
5. [Operate the FlowDevice](doc/operate-the-flow-device.md)
6. [Connect a client to the device](doc/connect-a-client.md)



### **Version 1.2.0**

* Raspberry Pi 3B+
* Waveshare Raspberry Pi High-Precision AD/DA
* Ubuntu Server 20.04 LTS 64-bit
* hipflowapp 1.1.0
* hipserver 3.9.0

