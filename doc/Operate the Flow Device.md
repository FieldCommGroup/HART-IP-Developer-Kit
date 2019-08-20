# Operate the Flow Device

The following instructions assume that you are operating the flow device from a Windows PC using the Windows HART-IP Client.

## Start the Flow Device

The flow device is a complete HART device and conforms to the HART protocol requirements.  It is implemented as a HART-IP Server application that runs on the Pi computer.  

You can launch the device from your PC as follows:

1. connect to the Pi using the [PuTTY client](https://www.putty.org/) using the IP address that you captured when you installed the OS.

2. login to the Pi using the user that you configured with superuser privileges.

3. In the terminal, move to the flow device folder and launch the server.  Leave tjhe server running in the window while you access it with your windows client.
```
    cd ~/flowdevice
    sudo hipserver hipflow
```
4. If the server fails to launch, make sure that your login has superuser privileges and the the two programs have execution permissions.
```
    ls -l 
    -rwxr-xr-x 1 tim tim 399440 Aug 20 13:39 hipserver
    # the x's on this line show the file i executable
```

5. We will use git to download the HART-IP client.  If you need git on your PC, you can get it for free [here](https://gitforwindows.org/).

6. Download the Windows HART-IP client repository using git from the Windows command prompt:
```
    git clone https://github.com/FieldCommGroup/WindowsHartIpClient
```

7. Install the client from the Windows command line:
```
    cd WindowsHartIpClient\Install\Release
    setup
```

8. To launch the client from the Windows Start menu, go to FieldComm Group/HART-IP Client.  The instructions for operating the client are available in this kit [here](https://github.com/FieldCommGroup/WindowsHartIpClient).

![useclient]()

9. Click the network button to connect to the running flow device.  Use the IP address of the device and use UDP option to connect to it.  The hipserver component only answers UDP at this time.  
![connect]()

10.  Click the Send button on the clientto send a command 0 to the device.

11. To close the client, click the network button again.

12.  To close the server, go to the PuTTy terminal window that you left open earlier and type a Ctrl-C.  Allow the server to terminate completely before closing the terminal.