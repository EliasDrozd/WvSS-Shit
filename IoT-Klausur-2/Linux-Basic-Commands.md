# Linux Commands

#### Important Notice

! Due to the fact that WvSS uses different PC-Models of various vendors, configuring VirutalBox and the VMs-Network Adapter properly might differ.
The most important ways are described below !

## Netplan-Set Up

Case 1) -> VirtualBox required Network Adapter is "eth0" or similar for e.x. "eth32"

Case 2) -> VirtualBox required Network Adapter is "Schulnetzwerk"

## Preparing VM

To get most services up and running smoothly, it is recommended to at least use the following command, to get the latest driver-sets and 
patches for the Debian Bookworm v3.iso, which is a standard Classtest .ISO File (except Win2022 Servers or Win10 VMs):

```
sudo su apt update
```

## Adapting Default / DHCP Network Interface

```
cd /etc/network/interfaces

nano interfaces.d
```

This file should contain by default the following Data:

```
auto enp0s3
iface enp0s3 inet dhcp
```
Change `inet dhcp` into `inet static`

## Adding the IP-Address

```
iface enp0s3 inet static

address 10.16.<Raumnummer>.<200 + PC ID) > bpsw. 10.16.225.214 (Raum 225, PC-ID: 214)
gateway 10.16.1.245
```

To accept the changes and use the new Netplan Configuration do the following:

`systemctl restart networking`

## Adapting the DNS-Config

```
nano /etc/resolv.conf

<resolv.conf>
nameserver 10.16.1.253
```
