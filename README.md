![FCG](https://avatars0.githubusercontent.com/u/26013747?s=100&v=4) Fieldcomm Group
=====================

# HART-IP-Developer-Kit

Accelerate your HART-IP development project with this kit.

Paragraph describing the kit contents…

# Included GitHub Repositories

| **Repository**                                                                  | **Description**                                                                                                                                                                                                                                                                                                                                           |
|---------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient) | Construct and send HART messages to a HART-IP device. Parse the responses. Subscribe to published messages. C\# project with user interface, UDP/TCP connection components and installer.                                                                                                                                                                 |
| [Hipserver](https://github.com/FieldCommGroup/hipserver)                        | Use this project to simplify the development of your own server application of HART-IP device. This component is shared by all FieldComm Group HART-IP server implementations, including the latest HART Test System. It manages IP connections, publishing messages to multiple clients and more. C++ project for Ubuntu operating systems 12 and later. |
| hipnativeflow                                                                   | This example HART device application, together with the hipserver component, implements a functioning, native HART-IP device. This example is tailored for Raspberry Pi 3B+ or later. C++ project for Ubuntu 18.04 or later.                                                                                                                              |

# Related Documents

HART-IP Client Guide maybe?

Any Other docs that we would furnish?

# How to Build and Operate a HART-IP Flow Device on a Raspberry Pi Computer

1. Purchase a Rasberry Pi 3B+ single board computer.
2. Purchase a sensor board as described [here](https://github.com/FieldCommGroup/hipflow) and add it to your Pi .
2. Download the UbuntuMATE 18.04 operating system from [here](https://ubuntu-mate.org/raspberry-pi/).  Select the 32-bit version named ubuntu-mate-18.04.2-beta1-desktop-armhf+raspi-ext4.img.xz.
3. Install the OS onto the Pi using the instructions [here](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-kit-c-get-started#install-the-raspbian-operating-system-for-pi), but using the UbuntuMATE 18 OS instead of the Raspbian OS.
4. Connect a monitor, keyboard,  mouse and network cable to the Pi.  Follow the prompts to configure your Ubuntu OS as desired.
5. Download and build the hipserver program as described [here](https://github.com/FieldCommGroup/hipserver).
6. Download and build the hipflow program as described [here](https://github.com/FieldCommGroup/hipflow).
8. In a terminal window, determine the IP address of the Pi using the **ifconfig** command line.
9. In your home folder, create a subfolder named FlowDevice.  Copy the executables from the hipserver and hipflow projects intio this folder.
9. To launch the flow device, open a bash terminal as administrator and move to the FlowDevice folder.  Run the command line **hipserver hipflow** and leave it running unattended in the terminal.
10. To terminate the server, issue a Ctrl-C in the termininal or close the terminal windiow.
11. On a PC running Windows 7 or higher, pull a copy of the Windows HART-IP Client from [here](https://github.com/FieldCommGroup/WindowsHartIpClient) and install it on the PC.
12.  Start the HART-IP client program and connect to the flow device at using the IP address of the Pi using **UDP** at port **5094**.  You may need to configure the PC firewall to allow UDB traffic on the PC.
13.  Issue HART commands interactively to the flow device as desired using the HART-IP client.