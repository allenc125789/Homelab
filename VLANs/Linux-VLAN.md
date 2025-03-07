
## Description

Linux based segment of the network. These servers are administrated remotely by accessing them through the Hyper-Visor Proxmox on `home-ok-hv01p`, their application specific webpages, or through SSH.

## 🐧 VLAN 1, Linux: (192.168.0.10 - 99)/24

> *Physical Host*
- Hostname: `home-ok-hv01p`
- Model: Gigabyte Technology Co., Ltd. | GA-78LMT-S2
  - **OS:** Debian 12, running [Proxmox](https://www.proxmox.com/en/): KVM based Debian hypervisor.
> *Virtual Machines*
- Hostname: `home-ok-bw01p`
  - **OS:** Debian 12, running [Bitwarden](https://github.com/bitwarden/server): Self-hosted password manager and vault.
>
- Hostname: `home-ok-ro02p`
  - **OS:** Debian 12, running [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
>
- Hostname: `home-ok-na01d`
  - **OS:** Debian 12, running [TurtleNAS](https://github.com/allenc125789/TurtleNAS): Development server for an application that i'm building. It's design is to act as NAS software for Debian.
>
- Hostname: `home-ok-na01p`
  - **OS:** Debian 12, running [TurtleNAS](https://github.com/allenc125789/TurtleNAS): Production server for my application TurtleNAS. NAS for my portable devices.
>
- Hostname: `home-ok-ws01d`
  - **OS:** Debian 12, running [Nginx](https://nginx.org/en/): Development server for my website(blog).
>
- Hostname: `home-ok-ws01p`
  - **OS:** Debian 12, running [Nginx](https://nginx.org/en/): Production server for my webssite(blog).
>
- Hostname: `home-ok-de01p`
  - **OS:** Debian 12, running as a Desktop for personal use.
>
> *Disks*
- Hotswap1: `1TB HDD`
  - Storage for VM flies.
>
- Hotswap2: `2TB HDD`
  - Storage for Backups of VM files.
>
- internal: `1TB HDD`
  - Storage for Debian12/proxmox filesystem.
>
______________________________________________________________________________

## Gateway View

![Image of Proxmox on home-ok-hv01p](https://github.com/allenc125789/Homelab/blob/main/images/Screenshot%20from%202025-03-07%2013-47-34.png)

______________________________________________________________________________

[Return to Homelab mainpage.](https://github.com/allenc125789/Homelab#lan-19216801---924)
