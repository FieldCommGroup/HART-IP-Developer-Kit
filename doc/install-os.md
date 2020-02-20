# Install the Operating System

This kit comes with a pre-configured microSD card with the OS and Flow Device software pre-installed. Follow these instructions to configure a microSD card for your own flow device. These instructions assume that you are using a Windows PC to build the card.

1. Download the UbuntuMATE 18.04 operating system from [here](https://ubuntu-mate.org/raspberry-pi/).  Select either the 32-bit version named **ubuntu-mate-18.04.2-beta1-desktop-armhf+raspi-ext4.img.xz** or the 64-bit version named **ubuntu-mate-18.04.2-beta1-desktop-arm64+raspi3-ext4.img.xz**.

The paid version of this kit uses the 64-bit OS on the preinstalled card.

1. Extract the OS image from the .xz file. [7-Zip](https://www.7-zip.org/) is a free utility for this.
2. Connect the microSD card to a USB port. You may need an [adapter](https://www.amazon.com/SmartQ-C307-Portable-MicroSDHC-MicroSDXC/dp/B06ZYXR7DL) for this.
3. Write the disk image to the microSD card using the [Win32DiskImager](https://sourceforge.net/projects/win32diskimager/) utility. **Be sure** to specify the drive letter for your microSD card in the Device pull-down, so that you do not overwrite your computer's hard disk!

![diskimage](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/diskimage.png)

Follow the next steps to ready the new OS for use.

1. Remove the microSD card from the PC and insert it into the slot on the bottom of the Pi.
2. Connect an HDMI monitor, keyboard, mouse and network cable to the Pi. The network cable should be connected to your hub or router.  
3. Power up the device and follow the first-use prompts to configure your Ubuntu OS as desired. Configure one user with admin \(superuser\) privileges; the flow device must run with elevated privileges. Make sure your Pi is connected to the internet; this is required for several steps that follow.
4. Here is a good [tutorial](https://tutorials.ubuntu.com/tutorial/command-line-for-beginners#0) for Linux command line \(terminal\) usage, if you are unfamiliar.
5. From the Menu in the upper-left-hand corner of the display, choose System Tools, then MATE Terminal to launch the Linux terminal.
6. Run the ifconfig utility from the command line and record the IPv4 address of the device. The four byte address is on the eth0 entry, in the inet field.
7. Next, ssh connection is not enabled in Ubuntu 18 by default. Enable ssh access by running the commands below in a terminal. The 'sudo' command on each line invokes the elevated privileges required to install the ssh server. Do not skip the remove step, it is required.

   ```text
   sudo apt update
   sudo apt remove openssh-server
   sudo apt install openssh-server
   sudo systemctl enable ssh
   ```

8. Verify that the ssh is enabled by running the following command in a terminal. If the service is live, you should see a line containing "Active: active \(running\)" in the output.

   ```text
   sudo systemctl status ssh
   q
   ```

   Type a 'q' \(for quit\) at the terminal to terminate the status output.

9. You may now connect to the Pi remotely using ssh or PuTTY \(from a PC\). Use the address that you recorded in step 6, above.

