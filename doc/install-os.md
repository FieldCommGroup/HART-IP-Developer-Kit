# Install the Operating System

1. Follow the [instructions here](https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#1-overview) to configure the operating system on a microSD card for your flow device. 

1. Select **Ubuntu Server 20.04.2 LTS (RPI 3/4/400) 64-bit OS for arm64 architectures** under the "Other general purpose OS" menu. 

1. We recommend that you use a wired ethernet connection. Do not configure a static IP address (yet). To use the device provisioning features, connect to an 'simple' ethernet switch that DHCP disabled if present.

1. On first login you will change the password from default of user: ubuntu pw: ubuntu to user: ubuntu pw: localadmin

1. Be sure to record the IP address for the RPi using the tutorial instructions or use 'ip addr' after login to obtain the assigned IP address.

## Configure the OS for use on flow device node

Follow these steps to ready the new OS for use on a flow device.

1. Run the commands below to install necessary services. The 'sudo' command on each line invokes the elevated privileges required to install the ssh server. Do not skip the remove step, it is required.
   
   ```
   sudo apt remove unattended-upgrades
   sudo apt update
   sudo apt install net-tools
   sudo apt install openssl
   sudo apt install libssl-dev
   sudo apt install git-all
   sudo apt install build-seesential
   sudo apt install vsftpd
   sudo apt install libjsoncpp-dev
   sudo apt install ssh
   
   ```
1. Verify that the ssh is enabled by running the following command in a terminal. If the service is live, you should see a line containing "Active: active \(running\)" in the output.
   ```text
   sudo systemctl status ssh
   ```
1. You may now connect to the Pi remotely using ssh or PuTTY \(from a PC\). Use the address that you recorded in step 4, above.
1. Open port 5094 for tcp and udp connections.
   ```
   sudo ufw allow from any to any port 53 proto tcp
   sudo ufw allow from any to any port 53 proto udp
   ```
1. Follow the instructions here (https://github.com/FieldCommGroup/private.HART-IP-Developer-Kit/blob/release-20/doc/create-minimum-hartip-network.md) to complete the setup of your local field network.

## Configure the OS for use on DNSMASQ node

Follow these steps to ready the new OS for use on a flow device.

1. Run the commands below to install necessary services. The 'sudo' command on each line invokes the elevated privileges required to install the ssh server. Do not skip the remove step, it is required.
   
   ```
   sudo apt update
   sudo apt install net-tools
   sudo apt install ssh
   sudo apt remove unattended-upgrades
   
   ```
1. Verify that the ssh is enabled by running the following command in a terminal. If the service is live, you should see a line containing "Active: active \(running\)" in the output.
   ```text
   sudo systemctl status ssh
   ```
1. You may now connect to the Pi remotely using ssh or PuTTY \(from a PC\). Use the address that you recorded in step 4 at the start of the OS install, above.
1. Follow the instructions here (https://github.com/FieldCommGroup/private.HART-IP-Developer-Kit/blob/release-20/doc/create-minimum-hartip-network.md) to complete the setup of your local field network.


