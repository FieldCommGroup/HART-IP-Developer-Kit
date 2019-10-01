# Operate the Flow Device

## Background
The flow device is a complete HART device conforming to the HART protocol requirements.  It is implemented as a HART-IP Server application that runs on the Pi computer.  

The flow device is implemented as a pair of cooperating programs that both run on the Pi computer:
* **hipserver** manages HART-IP sessions with up to three clients and passes HART messages to and from the flow application.  It implements the network layer of the HART protocol.
* **hipflow** reads data from the A/D board and processes HART request, response, and burst messages.  It implements the application layer of the HART protocol.

## Launch and Terminate the Flow Device
The following instructions assume that you are operating it from a Windows PC. 
Launch the device from your PC as follows:

1. Connect to the Pi using the Windows [PuTTY client](https://www.putty.org/) using the IP address that you captured when you installed the OS.

2. Login to the Pi using the user name that you configured with superuser privileges.

3. In the terminal, move to the flow device folder and launch the server.  Leave the server running in the terminal while you access it with your windows client.
```
    cd ~/flowdevice
    sudo ./hipserver ./hipflow
```

5. At this point the flow device is running in the terminal.  Just let it run there until you are done using it with your HART-IP client program.  When you are complete, you can terminate the flow device by typing Ctrl-C in the terminal.  Then close the PuTTy terminal.


## Security

The HART-IP specification does not address security issues.  Security is the responsibility of the system integrator.  DO WE WANT TO ADDRESS THIS SUBJECT IN THE KIT?

## Troubleshooting

The flow device accesses Linux memory directly to communicate with the A/D board.  This requires elevated privileges. If the server fails to launch, make sure to use sudo to launch the device and that the login has superuser or "sudoer" privileges.

The device may fail to launch because the two programs have lost the execute attribute on their files.  This can happen while copying the files around between folders or systems.  To check the permissions, try:
```
    ls -l 
    -rwxr-xr-x 1 tim tim 399440 Aug 20 13:39 hipserver
    # the x's on this line show the file i executable
```
To add the execute permisions, try:
```
    cd ~/flowdevice
    chmod +x hip*
```


The HART-IP session with the flow device is stateful and it allows up to three simultaneous sessions.  If your client program connects to the flow device but it does not terminate its HART-IP connection (a crash, for instance), then the session is orphaned.  It will timeout after 10 minutes, logging a message in the PuTTY terminal and then the session will become available again.  

If you repeatedly connect clients to the device and they do not close their HART-IP connections, then the available pool of sessions will become exhausted and the device will refuse further connections.  In that case, you can close the PuTTY terminal, open another and launch a new flow device instance.