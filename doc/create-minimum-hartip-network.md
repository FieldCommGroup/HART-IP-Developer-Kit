# Create Minimum HART-IP Network

Components needed for minimal HART-IP Field Network:
1. RaspPI3B+ runnning Ubuntu Server 20.04 LTS for the node running DNSMASQ service for DNS and DCHP services
1. RaspPI3B+ runnning Ubuntu Server 20.04 LTS for the node running Flow device/hipserver
1. Simple network switch - DHCP service disabled
1. PC to run the Portable HIP Client with available wired NIC to connect to field network
1. PC running syslog server if syslogging is going to be used by the **hipserver**. Instructions for syslog server setup are here: https://github.com/FieldCommGroup/HART-IP-Developer-Kit/doc/syslog-server.md

## Instructions for configuring each of the nodes
1. For the node on network running dnsmasq service (Ubuntu Server 20.04 64bit OS)

   1. install dnsmasq service
      ```text
       $ sudo apt install dnsmasq
       ```
   1. stop existing DNS service listening on port 53
      ```text
      sudo systemctl disable systemd-resolved
      sudo systemctl stop systemd-resolved
       ```
   1. Enable dns service and dhcp services in dnsmasq service by editing dnsmasq config file /etc/dnsmasq.conf as follows (uncomment and edit):

      `domain-needed`

      `bogus-priv`

      `no-resolv` 

      `local=/local/` 

      `listen-address=::1,127.0.0.1,192.168.0.10` 

      `expand-hosts` 

      `domain=local` 

      `dhcp-range=192.168.0.100,192.168.0.200,24h` 

      `dhcp-option=option:router,192.168.0.1` 

      `dhcp-authoritative` 

      `dhcp-leasefile=/var/lib/dnsmasq/dnsmasq.leases`

   1. Then (Re)Start dnsmasq service: 

      `sudo systemctl restart dnsmasq`
   1. Set fixed ipv4 address on this device - suggest 192.168.0.10 (to match dnsmasq config file setting 'listen-address' below)

        Edit /etc/netplan/50-cloud-init.yaml 
         ```text
            network:
                ethernets:
                    eth0:
                        dhcp4: no
                        addresses:
                          - 192.168.0.10/24
                        optional: true
                version: 2
         ```
       After changes to netplan issue: 
       **NOTE** This command will change your ip address to a fixed ip address. Be prepared to reconnect to this node on your field network at 192.168.0.10.

      `$ sudo netplan apply` 

      Check ip addr using: 

      `$ ip addr` 

1. Configure flow device/hipserver node to use DCHP server to obtain ip address

   NOTE: To allow for a backup ip of 192.168.0.42 if dhcp is not available the static `addresses:` is added
   
        Edit /etc/netplan/50-cloud-init.yaml 
         ```text
            network:
                ethernets:
                    eth0:
                        dhcp4: yes
                        addresses:
                          - 192.168.0.42/24
                        optional: true
                version: 2
         ```
   After changes to netplan issue:
    `$ sudo netplan apply` 

   Check ip addr using: 

    `$ ip addr` 

3. Configure PC running Portable HART-IP client NIC connecting to field network set to use DHCP service or use an IP address on the same subnet as the field network so that nslookup can be done.

4. Basic network switch with DHCP disabled to connect all the nodes in field network via ethernet cables.

NOTE: From the technical specs of the original recommended router, Ubiquiti EdgeRouter, it doesn't appear to have an internal DNS server. It requires you to specify an external DNS server on the internet. This is why it is recommended to use the dnsmasq solution (both DNS and DHCP service).



Once you complete above setup you should see your nodes (hipservers) listed by hostname and associated ip addr on the node running dnsmasq service.

To view all current DHCP leases on field network issue this from the node running dnsmasq: 

`$ cat /var/lib/misc/dnsmasq.leases` 

`ubuntu@ubuntu:~ $ cat /var/lib/misc/dnsmasq.leases`
`1625130212 b8:27:eb:ac:14:fc 192.168.0.138 b8-27-eb-ac-14-fc ff:3e:f7:61:1f:00:02:00:00:ab:11:cd:86:4f:ba:ad:45:3e:e4`
`1625104081 e4:b9:7a:58:75:c3 192.168.0.163 HARTIPCLIENT 01:e4:b9:7a:58:75:c3`

This list should get updated for every hipserver hostname change due to longtag and/or process unit tag change.

 
