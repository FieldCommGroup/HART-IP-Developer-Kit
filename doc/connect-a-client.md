# Connect a Client to the Flow Device

This kit includes a simple Windows HART-IP client program that you can use to connect to the flow device and to send HART commands to it. Use these instructions to launch the client and connect to your flow device. Additional instuctions are included in the README for its repository.

1. We will use git to download the HART-IP client. If you need git on your PC, you can get it for free [here](https://gitforwindows.org/).
2. Download the Portable HART-IP Client repository using git from the Windows command prompt:

   ```text
    git clone https://github.com/FieldCommGroup/Portable-HART-IP-Client
   ```

3. Install the client from the Windows command line:

   ```text
    cd WindowsHartIpClient\Install\Release
    setup
   ```

4. To launch the client from the Windows Start menu, go to FieldComm Group/HART-IP Client. The instructions for operating the client are available [here](https://github.com/FieldCommGroup/WindowsHartIpClient).
5. [Launch](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/operate-the-flow-device.md) the FlowDevice if it is not already running.

![useclient](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/useclient.png)

1. Click the network button to connect to the running flow device.  Use the IP address of the device and the UDP option to connect to it.  The hipserver component only answers UDP at this time.  Note: you may need to configure Windows firewall to allow UDP traffic onto your PC.

![connect](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/media/connect.png)

1. In the Command field of the client application, type "0". Click the Send button on the client to send a command 0 to the device.
2. To close the HART-IP connection to the flow device, click the network button again.
3. To close the server, go to the PuTTy terminal window that you left open [earlier](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/configure-the-flow-device.md) and type a Ctrl-C twice. Allow the server to terminate completely before closing the terminal.

