# Homelab

**Description**

Planning and organization of my home network. I've designed my network with 2 segments isolated by VLANs. One mostly containing Windows devices and the other containing Linux devices.

The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independintly without confliction.


# LAN: (192.168.0.1 - 9)

- Hostname: `home-ok-ro01p`
  - Default routing tables and firewall.
  - [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
>
- Hostname: `home-ok-sw01p`
  - Managed Switch, activated with port based VLANs.
  - [VLAN 1- Linux](https://github.com/allenc125789/Homelab/blob/main/VLANs/Linux-VLAN.md): Linux VLAN segment. Designed around Linux based technologies.
  - [VLAN 2- Windows](https://github.com/allenc125789/Homelab/blob/main/VLANs/Windows-VLAN.md): Windows VLAN segment. Designed around Windows based technologies.


______________________________________________________________________________


