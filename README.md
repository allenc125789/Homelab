# Homelab

**Description**

As a part of my homelab, for the documentation I want to upload it to github for furutre reproduction, organization and planning. This space will be used to outline the various aspects of my project which utilizes many Open Source solutions to create a lightweight (and very cost effective!) user space. This project introduced me into a lot of new tools, and getting a deeper understanding of Networking services and their coexisting nature within the OSI Model. I just recently finished utilizing my central server to near 100% of it's resources, and near ready to start planning an upgrade on my infrastructure. This Repo will contain: 

(a) What I did

(b) What my fail-safe is

(c) What comes next.

# (a)What I have

## -Hosted Services & Software

**Server Management**

* [Bitwarden](https://github.com/bitwarden/server): A self-hosted password manager and vault.
* [Proxmox](https://www.proxmox.com/en/): A KVM based Debian hypervisor. 
* [Netbox](https://github.com/netbox-community/netbox): A Network documentation program. Allows the tracking of IPs, Devices, and their status on the network.

**File storage & Sharing**

* [NetACBackup](https://github.com/allenc125789/NetACBackup.sh): My own script for NAS based backup management and storage.

**Networking**

* [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
* [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
* [FreeDNS](https://freedns.afraid.org): A third party DDNS service to track my home's dynamic public IP.

Most of these services are self hosted and virtualized in a Proxmox environment. My system is like this for a few security based aspects: Self hosted services can reduce the risk of hacks and data-leaks while data is traversing to an off-site location, and possible bad actors from accessing your private files. Virtualized environments reduce cost of needing multiple systems for multiple platforms, and will also increase my overall security by isolation of individual services.

## -Hardware

Currently my central server does most of the magic as a Proxmox Hypervisor. It consists of a 6 core CPU, 12G DDR3 RAM, and two 1T hard drives. There are some limitations with this setup, such as the motherboard has no IOMMU support, which makes pass-through of PCI(e) devices impossible for projects such as a GPU passthrough for a gaming VM, or a Network Card passthrough for my virtual router. Another limitation I face is the number of VM's I can safley make without over-use of resources. I'd be limited to 6 VM's total with 1 core per VM. With these limitations in mind, I can make the most out of my system.

All of my homelab's devices and VM's are listed here, and via the pictures below (Documentation tracked and logged via Netbox):

**Devies**

**Virtual Machines**

## -Network

Designing my network was made extremley easy with Netbox. After determinging the number of devices I have, I decided to go with a /26 subent, as it (1) will allow growth if I decide to add more devices to my network without being too unessesarily large, and (2) helps ease the process of organizing.

**Network Map**

**IP Ranges**

**IP Reservations**

**VLANS**

Work in progress. Will update soon.

**Monitoring**

Work in progress. Will update soon.

## -Automation

**The Linux Shell**

**My Script**

