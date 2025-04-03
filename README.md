# Homelab

**Description**

My homelab. Ganna try to keep it running as long as possible!

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

![Network Map.](https://github.com/allenc125789/Homelab/blob/main/images/Network-FlowChart.pn)
______________________________________________________________________________

# Recent Additions

I just introduced a new web server for my blog, on the subject of Electrical Engineering.
