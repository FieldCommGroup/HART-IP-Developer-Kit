# Factory reset

Description:  The hipserver is has a factory reset where the system settings per the HART Network Management Specification (https://library.fieldcommgroup.org/20085/TS20085) are reset to factory default.

Factory reset utilizes two pins brought up from the RaspPI3B+ to the Waveshare "High-Precision AD-DA" show in (1).

<img src="https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/Screen%20Shot%202019-10-07%20at%2012.05.34%20.png" width=60%>

Procedure:
1. Connect a jumper between GND and SDA (GPIO2) on Waveshare board.
1. Power cycle hipserver

    - The hipserver/device will come up with Long Tag (and Hostname) set to MAC address of the primary network interface controller (NIC) in the format:  **XX-XX-XX-XX-XX-XX** such as **b8-27-eb-27-85-40**.

    - The device should be registered on DNS service with that hostname so that a dnslookup can be done by the Portable HART-IP client.

1. Remove jumper so subsequent resets will not invoke factory reset.

1. Proceed with Initial Device Provisioning (TODO add link here) process before any further restart is done.
