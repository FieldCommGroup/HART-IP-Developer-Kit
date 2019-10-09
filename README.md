![FCG](https://avatars0.githubusercontent.com/u/26013747?s=100&v=4) Fieldcomm Group
=====================

# HART-IP Developer Kit
{{TOC}}

![pi_image](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/RaspberryPi3B%2BDiagram.png)

Accelerate your HART-IP development project with this kit. Paragraph describing the kit contents…

## How to Build and Operate a HART-IP Flow Device on a Raspberry Pi Computer

Follow the instructions in these guides to build and operate your device:
* [Purchase your parts using the Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Bill%20of%20Materials.md)
* [Install an operating system on your Pi Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md)
* [Configure the flow device software on the Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Configure%20the%20Flow%20Device.md)
* [Operate the flow device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Operate%20the%20Flow%20Device.md)
* [Connect a client to the device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Connect%20a%20Client.md)

## Kit Contents

| **Item** | **Link** | **Description** | **Status**|
|----------|----------|-----------------|-----------|
| Guidance | Flow Device Specification | what it does |  Draft.  PDF or md?  On github or support site?|
| Guidance | [Install the OS on the Raspberry Pi](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md) | Install the Ubuntu operating system on the Pi.| Draft md on github |
| Guidance | [Configure the Flow Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Configure%20the%20Flow%20Device.md) | How to build the flow device from source using this kit and how to configure and operate it.| Draft md on github |
| Guidance | [Operate the Flow Device](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Operate%20the%20Flow%20Device.md) | Launch the Flow Device software on the Pi.| Draft md on github |
| Guidance | [Connect a Client](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Connect%20a%20Client.md) | Download a free HART-IP client program and connect it to the Flow Device.| Draft md on github |
| Guidance | HART-IP Client Guide | Wally's document summarizing accessing a HART-IP device.|    Close to final.  PDF  On FCG website|
| Guidance | HART-IP Server Developer Guide | Tim's doc describing how to develop a new server using this kit. | Working.  PDF or md?  On github or support site?|
| Guidance | [Bill of Materials](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Bill%20of%20Materials.md) | Parts you need to build this kit | Draft |
|Repository| [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient) | Construct and send HART messages to a HART-IP device. Parse the responses. Subscribe to published messages. C\# project with user interface, UDP/TCP connection components and installer.| final|
|Repository| [hipserver](https://github.com/FieldCommGroup/hipserver)| Use this project to simplify the development of your own server application of HART-IP device. This component is shared by all FieldComm Group HART-IP server implementations, including the latest HART Test System. It manages IP connections, publishing messages to multiple clients and more. C++ project for Ubuntu operating systems 12 and later. | Close to final |
|Repository| [hipflow](https://github.com/FieldCommGroup/hipflow)    | This example HART device application, together with the hipserver component, implements a functioning, native HART-IP device. This example is tailored for Raspberry Pi 3B+ or later. C++ project for Ubuntu 18.04 or later. | working|
| System | Supplied | Fully assembled Raspberry Pi 3B+ with A/D board, enclosure and operating software installed. | working |




