![FCG](https://avatars0.githubusercontent.com/u/26013747?s=100&v=4) Fieldcomm Group
=====================

# HART-IP Developer Kit

Accelerate your HART-IP development project with this kit.

Paragraph describing the kit contents…

## Included GitHub Repositories

| **Repository**                                                                  | **Description**                                                                                                                                                                                                                                                                                                                                           |
|---------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Windows HART-IP Client](https://github.com/FieldCommGroup/WindowsHartIpClient) | Construct and send HART messages to a HART-IP device. Parse the responses. Subscribe to published messages. C\# project with user interface, UDP/TCP connection components and installer.                                                                                                                                                                 |
| [hipserver](https://github.com/FieldCommGroup/hipserver)                        | Use this project to simplify the development of your own server application of HART-IP device. This component is shared by all FieldComm Group HART-IP server implementations, including the latest HART Test System. It manages IP connections, publishing messages to multiple clients and more. C++ project for Ubuntu operating systems 12 and later. |
| [hipflow](https://github.com/FieldCommGroup/hipflow)                                                                   | This example HART device application, together with the hipserver component, implements a functioning, native HART-IP device. This example is tailored for Raspberry Pi 3B+ or later. C++ project for Ubuntu 18.04 or later.                                                                                                                              |

## Related Documents

HART-IP Client Guide maybe?

Any Other docs that we would furnish?

## How to Build and Operate a HART-IP Flow Device on a Raspberry Pi Computer

Follow the instructions in these guides (located in he doc/ folder) to construct your device:
* Purchase your parts using the Bill of Materials
* Install an oerating system on your Pi Device
* Configure the flow device software on the Pi
* Operate the flow device
* Connect a client to the device






9. To launch the flow device, open a bash terminal as administrator and move to the FlowDevice folder.  Run the command line **hipserver hipflow** and leave it running unattended in the terminal.
10. To terminate the server, issue a Ctrl-C in the termininal or close the terminal windiow.
11. On a PC running Windows 7 or higher, pull a copy of the Windows HART-IP Client from [here](https://github.com/FieldCommGroup/WindowsHartIpClient) and install it on the PC.
12.  Start the HART-IP client program and connect to the flow device at using the IP address of the Pi using **UDP** at port **5094**.  You may need to configure the PC firewall to allow UDB traffic on the PC.
13.  Issue HART commands interactively to the flow device as desired using the HART-IP client.