<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/FCG_logo_horizontal_color_lg600px.png" width=40% align=right>
# README
# HART-IP Developer Kit

## Introduction
HART-IP enabled products have been available since 2009.  To date the cast majority of products have been remote I/O.  This includes WirelessHART Gateways, HART 4-20ma I/O, and Remote Terminals Units (RTUs).

The HART-IP Developer Kit provides a complete working demonstration of a HART-IP field device.  Field Devices have long been supported by the HART-IP but are just now gaining interest in the HART community and industry. This kit provides a complete working hart-ip based flow device. The kit consists of two software modules running on a Raspberry Pi hardware platform. 

The two software modules are the:

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/IMG_1950-cropped-1.png" width=40% align=right title="Raspberry Pi 3B+"> 
- **HART-IP Server (hipserver)**  The hipserver component is essentially a HART-IP communication stack.  It takes care of all HART-IP specific functions plus manages client subscriptions.  The client subscriptions allow the hipserver to push the process and status data to client applications.

- **Flow Device Application (hipflowapp)**  The hipflowapp implements a complete flowmeter.  The HART-IP Developer kit includes an ADC/DAC board that provides the physical connection for the hipflowapp. Since the HART Application Layer is independent of the underlying communication media this also provides and example of a complete HART-enabled field device. 

These two software modules target operation under Ubuntu Linux and are each found in their own repository.  

This kit provides a simple way to evaluate HART-IP operation and learn the details needed to implement it in a field device (or even an I/O) 

## About this repository
This repository serves provides the core documentation and instructions for the HART-IP Developer Kit.  This includes directions for purchasing and assembling the kit, instructions for installing and operating the HART-IP Flow Device, and specifications for the HART-IP Flow Device itself.  Links are provided to companion repositories including the [hipserver](https://github.com/FieldCommGroup/hipserver), [hipflowapp](https://github.com/FieldCommGroup/hipflowapp) and the [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient).  The Windows HART-IP Client is a simple host application that can be used to communicate with and operate the HART-IP Flow Device.



### How to Build and Operate a HART-IP Flow Device on a Raspberry Pi Computer

Follow the instructions in these guides to build and operate your device:

* [Read the Flow Device Specification](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/hart-ip-flowdevice-spec.md)
* [Purchase your parts using the Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/bill-of-materials.md)
* [Install an operating system on your Pi Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md)
* [Configure the Flow Device software on the Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md)
* [Operate the Flow Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md)
* [Connect a client to the device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/connect-a-client.md)

### Kit Contents

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Item</b>
      </th>
      <th style="text-align:left"><b>Link</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
      <th style="text-align:left"><b>Format</b>
      </th>
      <th style="text-align:left">Where</th>
      <th style="text-align:left">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Public</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/hart-ip-flowdevice-spec.md">Flow Device Specification</a>
      </td>
      <td style="text-align:left">what it does</td>
      <td style="text-align:left">md</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">needs status section</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/bill-of-materials.md">Bill of Materials</a>
      </td>
      <td style="text-align:left">Parts you need to build this kit</td>
      <td style="text-align:left">md</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/install-os.md">Install the OS on the Raspberry Pi</a>
      </td>
      <td style="text-align:left">Install the Ubuntu operating system on the Pi.</td>
      <td style="text-align:left">md</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md">Configure the Flow Device</a>
      </td>
      <td style="text-align:left">Build the Flow Device from source and configure it.</td>
      <td style="text-align:left">md</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md">Operate the Flow Device</a>
      </td>
      <td style="text-align:left">Launch the Flow Device software on the Pi.</td>
      <td style="text-align:left">md</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/connect-a-client.md">Connect a Client</a>
      </td>
      <td style="text-align:left">Download a HART-IP client program and connect it to the Flow Device.</td>
      <td
      style="text-align:left">md</td>
        <td style="text-align:left">github</td>
        <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left">HART-IP Client Guide</td>
      <td style="text-align:left">Wally&apos;s document summarizing accessing a HART-IP device.</td>
      <td
      style="text-align:left">pdf</td>
        <td style="text-align:left">web</td>
        <td style="text-align:left">draft</td>
    </tr>
    <tr>
      <td style="text-align:left">Repository</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/WindowsHartIpClient">Windows HART-IP Client</a>
      </td>
      <td style="text-align:left">C# source code for a Windows-based HART-IP client. Installer is included.</td>
      <td
      style="text-align:left">git</td>
        <td style="text-align:left">github</td>
        <td style="text-align:left">final</td>
    </tr>
    <tr>
      <td style="text-align:left">Repository</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/hipserver">hipserver</a>
      </td>
      <td style="text-align:left">C++ source code for the HART-IP server component.</td>
      <td style="text-align:left">git</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">wait wally review readme</td>
    </tr>
    <tr>
      <td style="text-align:left">Repository</td>
      <td style="text-align:left"><a href="https://github.com/FieldCommGroup/hipflowapp">hipflowapp</a>
      </td>
      <td style="text-align:left">C++ source code for the HART-IP Flow Device application.</td>
      <td style="text-align:left">git</td>
      <td style="text-align:left">github</td>
      <td style="text-align:left">
        <p>wait steve bug</p>
        <p>wait steve readme</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Download</td>
      <td style="text-align:left">
        <p>FieldComm Group</p>
        <p>need link</p>
      </td>
      <td style="text-align:left">FDI Device Package and Encoded DD</td>
      <td style="text-align:left">d/l</td>
      <td style="text-align:left">repo</td>
      <td style="text-align:left">wait DD tasks</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Paid</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">SSD</td>
      <td style="text-align:left">ship</td>
      <td style="text-align:left">microSD w/Flow Device pre-installed</td>
      <td style="text-align:left">uSD</td>
      <td style="text-align:left">ship</td>
      <td style="text-align:left">wait final build</td>
    </tr>
    <tr>
      <td style="text-align:left">Download</td>
      <td style="text-align:left">need link</td>
      <td style="text-align:left">EDD source code</td>
      <td style="text-align:left">ddl</td>
      <td style="text-align:left">web</td>
      <td style="text-align:left">wait DD tasks</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left">need link</td>
      <td style="text-align:left">Flow Device Developer Guide</td>
      <td style="text-align:left">pdf</td>
      <td style="text-align:left">web</td>
      <td style="text-align:left">wait steve</td>
    </tr>
    <tr>
      <td style="text-align:left">Guidance</td>
      <td style="text-align:left">need link</td>
      <td style="text-align:left">Assembly and Operating Instruction Set</td>
      <td style="text-align:left">pdf</td>
      <td style="text-align:left">web</td>
      <td style="text-align:left">draft</td>
    </tr>
  </tbody>
</table>### Version History

#### Version 1.0

Initial release

* Raspberry Pi 3B+
* UbuntuMATE 18.04 LTS 64-bit
* Flow Device hipflowapp 1.0
* Server hipserver 3.6
* Windows HART-IP Client 1.0

