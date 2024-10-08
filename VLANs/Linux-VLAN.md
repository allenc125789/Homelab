
## Description

Linux based segment of the network. These servers are administrated remotely by accessing them through the Hyper-Visor Proxmox on `home-ok-hv01p`, their application specific webpages, or through SSH.

## 🐧 VLAN 1, Linux: (192.168.0.10 - 99)/24

> *Physical Hosts*
- Model: Lenovo | ThinkPad L14 Gen 3
- Hostname: `home-xx-pd01p`
  - **Debian 12**: Portable laptop, for basic web-browsing, work and administration.
>
- Model: Gigabyte Technology Co., Ltd. | GA-78LMT-S2
- Hostname: `home-ok-hv01p`
  - **Debian 12**: running [Proxmox](https://www.proxmox.com/en/): KVM based Debian hypervisor.
> *Virtual Machines --> home-ok-hv01p*
- Hostname: `home-ok-ro02p`
  - **Debian 12**: running [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
>
- Hostname: `home-ok-bw01p`
  - **Debian 12**: running [Bitwarden](https://github.com/bitwarden/server): Self-hosted password manager and vault.
>
- Hostname: `home-ok-na01d`
  - **Debian 12**: running [TurtleNAS](https://github.com/allenc125789/TurtleNAS): Development server for an application that i'm building. It's design is to act as NAS software for Debian.
>
- Hostname: `home-ok-de01p`
  - **Debian 12**: Desktop for personal use.
>
______________________________________________________________________________

## Gateway View

![Image of Proxmox on home-ok-hv01p](https://github.com/allenc125789/Homelab/blob/main/images/Screenshot%20from%202024-08-05%2022-05-49.png)

______________________________________________________________________________

[Return to Homelab mainpage.](https://github.com/allenc125789/Homelab#lan-19216801---924)
