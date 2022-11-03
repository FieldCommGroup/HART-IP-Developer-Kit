
# Syslog Server setup
Sample syslog server setup instructions using rsyslog (rsyslog.com)

Recommend configuring syslog server node below so that the syslog server can be located by the **Hipserver** using syslog server **hostname** (set via cmd 545).
1. Seperate node with dhcp enabled on the local field network so that it's hostname and ip address can be registered in DNS server running dnsmasq. Then the syslog server can be located by the **Hipserver** using syslog server **hostname** (set via cmd 545).

**-or-**

2. On the same node as the node running dnsmasq and put an entry in the /etc/hosts file with syslog name and ip addr of node along with uncomment entry 'expand-host' in /etc/dnsmasq.conf. Next edit /etc/hosts adding ip address of node running dnsmasq along with desired hostname of syslog server (assuming dnsmasq node is at 192.168.0.10)
```text
syslog-server 192.168.0.10
```

Install rsyslog on a PC on the network accessible by the **Hipserver**. Example here is for a PC runnning Ubuntu 20.
```text
$ sudo apt install rsyslog
```
Start/enable rsyslog 
```text
$ sudo systemctl start rsyslog   
$ sudo systemctl enable rsyslog   
$ sudo systemctl status rsyslog
```
Modify rsyslog config /etc/rsyslog.conf by uncommenting and/or adding the following lines:
```text 
module(load="imuxsock")
module(load="imjournal")
module(load="imudp")
input(type="imudp" port="514")
module(load="imtcp")
input(type="imtcp" port="514")
$template RemoteLogs,"/var/log/%HOSTNAME%/%PROGRAMNAME%.log" 
*.* ?RemoteLogs
```
Restart rsyslog
```text
$ sudo systemctl restart rsyslog
```
After setting up **Hipserver** syslog, syslog entries can be found here /var/log/messages on the PC running rsyslog.
