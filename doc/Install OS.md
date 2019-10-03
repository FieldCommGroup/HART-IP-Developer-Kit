# Install the Operating System

Follow these instructions to configure the microSD card for your flow device.  These instructions assume that you are using a Windows PC to build the card.

1. Download the **UbuntuMATE 18.04** operating system from [here](https://ubuntu-mate.org/raspberry-pi/).  Select the 32-bit version named ubuntu-mate-18.04.2-beta1-desktop-armhf+raspi-ext4.img.xz.

2. Extract the OS image from the .xz file.  [7-Zip](https://www.7-zip.org/) is a free utiity for this.

3. Connect the microSD card to a USB port.  You may need an [adapter](https://www.amazon.com/SmartQ-C307-Portable-MicroSDHC-MicroSDXC/dp/B06ZYXR7DL) for this.

4. Write the disk image to the microSD card using the [Win32DiskImager](https://sourceforge.net/projects/win32diskimager/) utility.  **Be sure** to specify the drive letter for your microSD card in the Device pull-down, so that you do not overwrite your computer's hard disk!
![diskimage](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/diskimage.png)


Follow the next steps to ready the new OS for use.

5. Remove the microSD card from the PC and insert it into the Pi slot on the bottom of the unit.

6. Connect a monitor, keyboard, mouse and network cable to the Pi.  

7. Power up the device and follow the first-use prompts to configure your Ubuntu OS as desired.  Configure one user with admin (superuser) priviledges;  the flow device has to run with elevated priviledges.

8. Here is a good [tutorial](https://tutorials.ubuntu.com/tutorial/command-line-for-beginners#0) for Linux command line (terminal) usage, if you are unfamiliar.

9. From the Menu in the upper-lefthand corner of the display, choose System Tools, then MATE Terminal to launch the Linux terminal.

10. Run the ifconfig utility from the command line and record the IPv4 address of the device.  The four byte address is on the eth0 entry, in the inet field.
