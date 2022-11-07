# Configure the Flow Device

The paid version of this kit includes pre-compiled flow device software for your convenience. The pre-built software is built using the Ubuntu version specified on the [Install the OS](../doc/Install%20OS.md) page.

To build the flow device software from source and configure the device yourself, use the following instructions.

## Install Developer Tools

To build the flow device software yourself, you will need to install the developer tools first \(compiler, make, etc.\). Then in the next section, you will download the code from the repository and build the two programs.

We will install the developer tools using sudo \(admin\) privileges.

1. Install git source code control

   ```text
    sudo apt update
    sudo apt install git
    git --version
    # produces version 2.25 or higher
   ```

2. Install g++ compilers

   ```text
    sudo apt update
    sudo apt install build-essential
    g++ -v
    # produces version 9.3 or higher
    make -v
    # produces version 4.2.1 or higher
   ```

## Build from Source

1. Download and build the hipserver program:

   ```text
    mkdir ~/flowdevice
    cd ~
    git clone https://github.com/FieldCommGroup/hipserver
    cd hipserver/hipserver/Server/
    make
    cp hipserver ~/flowdevice
   ```

2. Download and build the hipflow program:

   ```text
    cd ~
    git clone --recurse-submodules https://github.com/FieldCommGroup/hipflowapp
    cd hipflowapp/hipflowapp/Hip_Native/
    make
    cp hipflowapp ~/flowdevice
   ```

