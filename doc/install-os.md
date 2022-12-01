# Install the Operating System

The paid kit comes with a pre-configured microSD card with the OS and Flow Device software pre-installed. Follow these instructions to configure a microSD card for your own flow device. These instructions assume that you are using a Windows PC to build the card.

1. Connect the microSD card to a USB port. You may need an [adapter](https://www.amazon.com/SmartQ-C307-Portable-MicroSDHC-MicroSDXC/dp/B06ZYXR7DL) for this.
2. Download and install the free [Raspberry Pi Imager](https://www.raspberrypi.com/news/raspberry-pi-imager-imaging-utility/) utility on your PC.  Use it to intall the Ubuntu 20.04 LTS (64 bit) server operating system on your SD Card.

![diskimage](https://www.raspberrypi.org/app/uploads/2020/03/RPI_intro-e1583228263677.png)

Follow the next steps to ready the new OS for use.

1. Remove the microSD card from the PC and insert it into the slot on the bottom of the Pi.
2. Connect an HDMI monitor, keyboard, mouse and network cable to the Pi. The network cable should be connected to your hub or router.  
3. Power up the device and follow the first-use prompts to configure your Ubuntu OS as desired. Make sure your Pi is connected to the internet; this is required for several steps that follow.
4. Here is a good [tutorial](https://tutorials.ubuntu.com/tutorial/command-line-for-beginners#0) for Linux command line \(terminal\) usage, if you are unfamiliar.
5. Run the command line "ip addr" from the terminal and record the IPv4 address of the device. The four byte address is on either the eth1 or eth2 entry, in the inet field.
6. Connect to the Pi remotely using ssh or PuTTY \(from a PC\). Use the address that you recorded in step 5, above.
