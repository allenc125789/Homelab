## -Description

As a part of my homelab, for the documentation I want to upload it to github for furutre reproduction, organization and planning. This space will be used to outline the various aspects of my project which utilizes many Open Source solutions to create a lightweight (and very cost effective!) user space. This project introduced me into a lot of new tools, and getting a deeper understanding of Networking services and their coexisting nature within the OSI Model. I just recently finished utilizing my central server to near 100% of it's resources, and near ready to start planning an upgrade on my infrastructure. This Repo will contain: What I did; What my fail-safe is; and what comes next.

## -Hosted Services & Software

**Server Management**

* [Bitwarden](https://github.com/bitwarden/server): A self-hosted password manager and vault.
* [Proxmox](https://www.proxmox.com/en/): A KVM based Debian hypervisor.

**File storage & Sharing**

* [NetACBackup](https://github.com/allenc125789/NetACBackup.sh): My own script for NAS based backup management and storage.

**Networking**

* [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
* [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
* [FreeDNS](https://freedns.afraid.org) - A third party DDNS service to track my home's dynamic public IP.

Most of these services are self hosted and virtualized environment in Proxmox. Most of my services are like this for a few security based aspects: Self hosted services reduces the risk of hacks and data-leaks while data is traversing to an off-site infrastructure, and possible bad actors from accessing your private files. Virtualized environments reduce cost of needing multiple systems for multiple platforms, and also increase my overall security by isolation of individual services.

## -Hardware

Currently my central server does most of the magic as a Proxmox Hypervisor. It consists of a 6 core CPU, 12G DDR3 RAM, and two 1T hard drives. There are some limitations with this setup, such as the motherboard has no IOMMU support, which makes pass-through of PCI(e) devices impossible for projects such as a GPU passthrough for a gaming VM, or a Network Card passthrough for my virtual router. Another limitation I face is the number of VM's I can safley make without over-use of resources. I'd be limited to 6 VM's total with 1 core per VM. 

All of my homelab's devices and VM's are listed here, and via the pictures below (Documentation tracked and logged via Netbox):

**Devies and Virtual Machines**

## -Network
