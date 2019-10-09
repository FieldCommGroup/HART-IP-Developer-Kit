# Configure the Flow Device


We include pre-compiled fow device software in this kit for your convenience.  The pre-built software is built using the Ubuntu version specfied on the [Install the OS](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md) page.  If you are using a diferent version of the OS, you will need to pull and build the execuatbles yourself using the instructions below.


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
    git clone --recurse-submodules https://github.com/FieldCommGroup/hipflow
    cd hipflowapp/hipflowapp/Hip_Native/
    make
    cp hipflow ~/flowdevice
```
