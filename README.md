# README

![](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/FCG_logo_horizontal_color_lg600px.png)

## README

## HART-IP Developer Kit

### Introduction

HART-IP enabled products have been available since 2009. To date the cast majority of products have been remote I/O. This includes WirelessHART Gateways, HART 4-20ma I/O, and Remote Terminals Units \(RTUs\).

The HART-IP Developer Kit provides a complete working demonstration of a HART-IP field device. Field Devices have long been supported by the HART-IP but are just now gaining interest in the HART community and industry. This kit provides a complete working HART-IP based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform.

![](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/IMG_1950-cropped-1.png)

The two software modules are the:
* **HART-IP Server \(hipserver\)** The hipserver component is essentially a HART-IP communication stack. It takes care of all HART-IP specific functions plus manages client subscriptions. The client subscriptions allow the hipserver to push the process and status data to client applications.
* **Flow Device Application \(hipflowapp\)** The hipflowapp implements a complete flowmeter. The HART-IP Developer kit includes an ADC/DAC board that provides the physical connection for the hipflowapp. Since the HART Application Layer is independent of the underlying communication media this also provides an example of a complete HART-enabled field device.

These two software modules target operation under Ubuntu Linux and are each found in their own repository.

This kit provides a simple way to evaluate HART-IP operation and learn the details needed to implement it in a field device \(or even an I/O\).

### About this repository

This repository serves provides the core documentation and instructions for the HART-IP Developer Kit. This includes directions for purchasing and assembling the kit, instructions for installing and operating the HART-IP FlowDevice, and specifications for the HART-IP FlowDevice itself. Links are provided to companion repositories including the [hipserver](https://github.com/FieldCommGroup/hipserver), [hipflowapp](https://github.com/FieldCommGroup/hipflowapp) and the [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient). The Windows HART-IP Client is a simple host application that can be used to communicate with and operate the HART-IP FlowDevice.

#### How to Build and Operate a HART-IP FlowDevice on a Raspberry Pi Computer

Follow the instructions in these guides to build and operate your device:

1. [Read the FlowDevice Specification](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/hart-ip-flowdevice-spec.md)
2. [Purchase your parts using the Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/bill-of-materials.md)
3. [Install an operating system on your Pi Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md)
4. [Configure the FlowDevice software on the Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md)
5. [Operate the FlowDevice](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md)
6. [Connect a client to the device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/connect-a-client.md)

#### Kit Contents

| **Item** | **Link** | **Description** | **Format** | Where | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Public** |  |  |  |  |  |
| Guidance | [Flow Device Specification](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/hart-ip-flowdevice-spec.md) | what it does | md | github | needs status section |
| Guidance | [Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/bill-of-materials.md) | Parts you need to build this kit | md | github | final |
| Guidance | [Install the OS on the Raspberry Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md) | Install the Ubuntu operating system on the Pi. | md | github | final |
| Guidance | [Configure the Flow Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md) | Build the Flow Device from source and configure it. | md | github | final |
| Guidance | [Operate the Flow Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md) | Launch the Flow Device software on the Pi. | md | github | final |
| Guidance | [Connect a Client](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/connect-a-client.md) | Download a HART-IP client program and connect it to the Flow Device. | md | github | final |
| Guidance | HART-IP Client Guide | Wally's document summarizing accessing a HART-IP device. | pdf | web | draft |
| Repository | [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient) | C\# source code for a Windows-based HART-IP client. Installer is included. | git | github | final |
| Repository | [hipserver](https://github.com/FieldCommGroup/hipserver) | C++ source code for the HART-IP server component. | git | github | wait wally review readme |
| Repository | [hipflowapp](https://github.com/FieldCommGroup/hipflowapp) |C++ source code for the HART-IP Flow Device application.| git | github | wait tim edit|  
|Download| FieldComm Group need link | FDI Device Package and Encoded DD | D/L | repo | wait DD tasks |
| **Paid** | | | | | | 
| SSD | ship | microSD w/Flow Device pre-installed | uSD | ship | wait final build |
| Download | need link | EDD source code | ddl | web | wait DD tasks |
| Guidance | need link | Flow Device Developer Guide | pdf | web | wait tim edit |
| Guidance | need link | Assembly and Operating Instruction Set (User Guide)| pdf | web | draft |


#### **Version 1.0.0**

Initial release

* Raspberry Pi 3B+
* UbuntuMATE 18.04 LTS 64-bit
* hipflowapp 1.0
* hipserver 3.6.1
* Windows HART-IP Client 1.0

