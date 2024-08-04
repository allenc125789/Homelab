# Homelab

- **Description**

Network plan, and organization of my home network. I've designed my network with 2 isolated segments, seperated by VLANs. One mostly containing Windows devices, and the other containing Linux devices. The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independintly without confliction.


# LAN (192.168.0.1 - 9)

- Hostname: *home-ok-ro01p*
  - [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.

______________________________________________________________________________


## Linux VLAN (192.168.0.10 - 99)

- Hostname: *home-ok-hv01p*
  - [Proxmox](https://www.proxmox.com/en/): KVM based Debian hypervisor. 

______________________________________________________________________________

- Hostname: *home-ok-ro02p*
  - [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.

______________________________________________________________________________

- Hostname: *home-ok-bw01p*
  - [Bitwarden](https://github.com/bitwarden/server): Self-hosted password manager and vault.

______________________________________________________________________________

- Hostname: *home-ok-na01p*
  - [TurtleNAS](https://github.com/allenc125789/TurtleNAS): My own application that i'm building, that acts as NAS software for Debian.

______________________________________________________________________________

- Hostname: *home-ok-de01p*
  - Debian Desktop for personal use.

______________________________________________________________________________

## Windows VLAN (192.168.0.100 - 149)

- home-ok-ws01p
  - Windows Server, running Active Directory and DNS roles.
 
______________________________________________________________________________

- home-ok-hv02p
  - Windows Server Core, running Hyper-V.

______________________________________________________________________________

- home-ok-de02p
  - Windows 11 Desktop, for general Administration

______________________________________________________________________________

