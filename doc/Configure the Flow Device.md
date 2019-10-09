# Configure the Flow Device


If you are using the microSD card that ships with this kit, then the flow device is already configured for you in the **~user1/flowdevice/** folder.


To build from source and configure the device yourself, use the following instructions.


## Install Developer Tools

To build the flow device software yourself, you will need to install the developer tools first (compiler, make, etc). Then in the next section, you will download the code from the repository and build the two programs.

We will install the developer tools using sudo (admin) priviledges.

1. Install git source code control
```
    sudo apt-get update
    sudo apt-get install git
    git --version
    # produces version 2.17
```

2. Install g++ compilers
```
    sudo apt-get update
    sudo apt-get install build-essential
    g++ -v
    # produces version 7.4
    make -v
    # produces version 4.1
```

## Install from Source

You will require a github account to access the repositories from the command line.  

1. Download and build the hipserver program:
```
    mkdir ~/flowdevice
    cd ~
    git clone https://github.com/FieldCommGroup/hipserver
    cd hipserver/hipserver/Server/
    make
    cp hipserver ~/flowdevice
```

2. Download and build the hipflow program:
```
    cd ~
    git clone --recursive https://github.com/FieldCommGroup/hipflow
    cd hipflowapp/hipflowapp/Hip_Native/
    make
    cp hipflow ~/flowdevice
```
