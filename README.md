# Homelab

**Description**

Network plan, and organization of my home network. I've designed my network with 2 isolated segments, seperated by VLANs. One mostly containing Windows devices, and the other containing Linux devices. The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independintly without confliction.

______________________________________________________________________________________________________________________________________________________________________________

# LAN

* home-ok-ro01p
[OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.


## Linux VLAN

* home-ok-hv01p
[Proxmox](https://www.proxmox.com/en/): KVM based Debian hypervisor. 

* home-ok-ro02p
[OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.

* home-ok-bw01p
[Bitwarden](https://github.com/bitwarden/server): Self-hosted password manager and vault.

* home-ok-na01p
[TurtleNAS](https://github.com/allenc125789/TurtleNAS): My own application that i'm building, that acts as NAS software for Debian.

* home-ok-de01p
Debian Desktop for personal use.


## Windows VLAN

* home-ok-ws01p

* home-ok-hv02p

* home-ok-de02p

home-ok-


