# Configure the Flow Device

The paid version of this kit includes pre-built flow device software for your convenience. It is built using the Ubuntu version specified on the [Install the OS](https://github.com/FieldCommGroup/HART-IP-Developer-Kit/blob/master/doc/Install%20OS.md) page.

To build the flow device software from source and configure the device yourself, use the following instructions.

## Install Developer Tools

You will need to install the developer tools first \(compiler, make, etc.\). This requires the use of sudo \(for admin privileges\).

Then in the next section, you will download the code from the repository and build the two programs.


Run the commands below to install necessary services. 
   
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
```

## Update OpenSSL

There was a security [vulnerability](https://www.openssl.org/news/secadv/20220315.txt) discovered in the OpenSSL library in March 2022. The current release of Ubuntu 20 does not yet contain the upgraded OpenSSL library that corrects the vulnerability.  Follow this procedure to update your OpenSSL:

```
sudo apt-get install -y wget cmake make gcc perl
wget https://www.openssl.org/source/openssl-1.1.1n.tar.gz -O - | tar -xz
cd openssl-1.1.1n
sudo ./config --prefix=/opt/openssl --openssldir=/opt/openssl/ssl
sudo make
sudo make install

#backup old ssl binary
sudo mv /usr/bin/openssl /usr/bin/openssl.old
#point to new openssl binary
sudo ln -s /opt/openssl/bin/openssl /usr/bin/openssl
```
Add a line to /etc/environment:

    LD_LIBRARY_PATH=/opt/openssl/lib

Logout or exit SSH then relogin for reconnect, then verify successful version update:
```
openssl version
#OpenSSL 1.1.1n  15 Mar 2022
```
You may need to run ldconfig after relocation if any problems encountered above.

Reference: https://github.com/openssl/openssl/issues/11227

## Build from Source

1. Download and build the hipserver program:

```text
cd ~
mkdir flowdevice
cd ~/flowdevice/
git clone https://github.com/FieldCommGroup/hipserver
cd hipserver/hipserver/Server/
make
```

2. Download and build the hipflow program:

```text
cd ~/flowdevice/
git clone --recurse-submodules https://github.com/FieldCommGroup/hipflowapp
cd hipflowapp/hipflowapp/Hip_Native/hipserver
git checkout master
cd ..
make
cp hipflowapp ~/
cd ~/flowdevice/hipflowapp/build-network/build-flow-device/
sudo cp 50-cloud-init.yaml /etc/netplan
cp reset.sh run.sh ~/
```

