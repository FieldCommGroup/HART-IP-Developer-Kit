# Configure the Flow Device

The paid version of this kit includes pre-built flow device software for your convenience. It is built using the Ubuntu version specified on the [Install the OS](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md) page.

To build the flow device software from source and configure the device yourself, use the following instructions.

## Install Developer Tools

You will need to install the developer tools first \(compiler, make, etc.\). This requires the use of sudo \(for admin privileges\).

Then in the next section, you will download the code from the repository and build the two programs.


1. Run the commands below to install necessary services. 
   
```
sudo apt remove unattended-upgrades
sudo apt update
sudo apt install net-tools
sudo apt install openssl
sudo apt install libssl-dev
sudo apt install git-all
sudo apt install build-essential
sudo apt install vsftpd
sudo apt install libjsoncpp-dev
sudo apt install ssh
```
2. Open port 5094 for tcp and udp connections.
```
sudo ufw allow from any to any port 53 proto tcp
sudo ufw allow from any to any port 53 proto udp
```

## Update OpenSSL

There was a security [vulnerability](https://www.openssl.org/news/secadv/20220315.txt) discovered in the OpenSSL library in March 2022. The current release of Ubuntu 20 does not yet contain the upgraded OpenSSL library that corrects the vulnerability.  To update your OS installation, download the updated library from [GitHub](https://github.com/openssl/openssl) and follow the instructions there.

## Build from Source

1. Download and build the hipserver program:

   ```text
    cd ~
    git clone https://github.com/FieldCommGroup/hipserver
    cd hipserver/hipserver/Server/
    make
   ```

2. Download and build the hipflow program:

   ```text
    cd ~
    git clone --recurse-submodules https://github.com/FieldCommGroup/hipflowapp
    cd hipflowapp/hipflowapp/Hip_Native/
    make
   ```

