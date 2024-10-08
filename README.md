# Homelab

**Description**

The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independently without confliction.

Contents include planning and organization of my home network. I've designed my network with 2 segments isolated by VLANs. One mostly containing Windows devices and the other containing Linux devices. My LAN is a /24 subnet, and has 254 IP address for use. The first 9 addresses are reserved for physical core routing devices and switches. The rest of the addresses will be split within VLANS.

# LAN: (192.168.0.1 - 9)/24

> *Physical Hosts*
- Model: TP-Link | AX1500 Wi-Fi 6 Router
- Hostname: `home-ok-ro01p`
  - Default routing tables and firewall.
  - [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
  - ⚠️ Ports Open ⚠️
    - 443 --> `192.168.0.121/home-ok-na03p` (HTTPS)
    - 1149 --> `localhost` (OpenVPN)
>
- Model: TP-Link | GS105Ev2 - 5-Port Gigabit Ethernet Smart Managed Plus Switch
- Hostname: `home-ok-sw01p`
  - Managed Switch, activated with port based VLANs.
    - **⤷** [🐧 VLAN 1, (Linux)](https://github.com/allenc125789/Homelab/blob/main/VLANs/Linux-VLAN.md#description): ***(Click to see the Linux VLAN segment)***. Designed around Linux based technologies. This VLAN is mostly dedicated to personal use and development.
    - **⤷** [🪟 VLAN 2, (Windows)](https://github.com/allenc125789/Homelab/blob/main/VLANs/Windows-VLAN.md#description): ***(Click to see the Windows VLAN segment)***. This VLAN is used as a testlab for simulating a Windows work domain environment controlled by Active Directory, with a public facing webserver running within Hyper-V.
______________________________________________________________________________

# Network Map

![Network Map.](https://github.com/allenc125789/Homelab/blob/main/images/Network-FlowChart.png)
______________________________________________________________________________

# Recent Additions

A few months ago, my uncle gifted me a `Dell PowerEdge T310` Server from an old work environment he was a Technician at. I was able to use this plus some old thinkpad laptops and a managed switch I had to construct the Window's environment segment on my home network. This recent addition allowed me to study a Enterprise level Dell server, and introduce Windows OS domain/network tools to a segment of computers while avoiding confliction from my services run on Linux, with the introduction of VLANs.
______________________________________________________________________________
