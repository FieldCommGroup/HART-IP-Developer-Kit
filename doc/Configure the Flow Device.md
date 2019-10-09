# Configure the Flow Device

Use these instructions to load the flow device software onto the Pi computer.

## Install from Pre-built Software

We include pre-compiled fow device software in this kit for your convenience.  The pre-built software is built using the Ubuntu version specfied on the [Install the OS](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md) page.  If you are using a diferent version of the OS, you will need to pull and build the execuatbles yourself using the instructions below.

1. Locate the hipserver and hipflow executables in the bin/ folder of this repository.

2. From a terminal, move to your home folder and create a sub-folder on the Pi named flowdevice.  Copy the two executables to the this folder.  Then mark them as executable.
```
    cd ~
    mkdir flowdevice

    # copy the binaries to this new folder, then

    sudo chmod +x hip*
```

## Install Developer Tools

To build the flow device software yourself, you will need to install the developer tools first (compiler, make, etc). Then in the next section, you will download the code from the repository and build the two programs.

We will install the developer tools with sudo (admin) priviledges.

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

You may require a github account to access the repositories from the command line.  Here are [instructions](https://help.github.com/en/articles/signing-up-for-a-new-github-account) for opening a free github account.

1. Download and build the hipserver program:
```
    cd ~
    git clone https://github.com/FieldCommGroup/hipserver
    cd hipserver/hipserver/Server/
    make
    mkdir ~/flowdevice
    cp hipserver ~/flowdevice
```

2. Download and build the hipflow program:
```
    cd ~
    git clone https://github.com/FieldCommGroup/hipflow
    cd hipflow/hipflow
    make
    cp hipflow ~/flowdevice
```
