# Homelab

**Description**

The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independently without confliction.

Contents include planning and organization of my home network. I've designed my network with 2 segments isolated by VLANs. One mostly containing Windows devices and the other containing Linux devices. My LAN is a /24 subnet, and has 254 IP address for use. The first 9 addresses are reserved for physical core routing devices and switches. The rest of the addresses will be split within VLANS.

# LAN: 192.168.0.1/24

> *Physical Hosts*
- Model: TP-Link | AX1500 Wi-Fi 6 Router
- Hostname: `home-ok-ro01p`
  - Default routing tables and firewall.
  - [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
  - ⚠️ Ports Open ⚠️
    - 443 --> `192.168.0.26/home-ok-ws01p` (HTTPS)
    - 1149 --> `localhost` (OpenVPN)
>
- Model: TP-Link | GS105Ev2 - 5-Port Gigabit Ethernet Smart Managed Plus Switch
- Hostname: `home-ok-sw01p`
  - Managed Switch.
    - **⤷** [🐧Linux Server](https://github.com/allenc125789/Homelab/blob/main/VLANs/Linux-VLAN.md#description) 
______________________________________________________________________________

# Network Map

![Network Map.](https://github.com/allenc125789/Homelab/blob/main/images/Network-FlowChart.png)
______________________________________________________________________________

# Recent Additions

I just introduced a new web server for my blog, on the subject of Electrical Engineering.
