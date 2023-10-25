# Homelab

**Goal**

My goals for this project as my first homelab was to get all my data organized, implement new technology to increase my home network's security and functionality, and create an automated system with reproduceable backups.

**Description**

As a part of my homelab, for the documentation I want to upload it to github for future reproduction, organization and planning. This space will be used to outline the various aspects of my project which utilizes many Open Source solutions to create a secure, lightweight (and very cost effective!) user space. This project introduced me into a lot of new tools, and getting a deeper understanding of Networking services and their coexisting nature within the OSI Model. I just recently finished utilizing my central server to near 100% of it's resources, and near ready to start planning an upgrade on my infrastructure. This Repo will contain: 

[1. What I Have.](https://github.com/allenc125789/Homelab/blob/main/README.md#awhat-i-have)

- 1a. 

   - 1b.

  - 1c.

  - 1d.

  - 1e.

[2. What is my fail-safe?

[3. What comes next?

# (a)What I Have.

## -Hosted Services & Software

**Server Management**

* [Bitwarden](https://github.com/bitwarden/server): A self-hosted password manager and vault.
* [Proxmox](https://www.proxmox.com/en/): A KVM based Debian hypervisor. 
* [Netbox](https://github.com/netbox-community/netbox): A Network documentation program. Allows the tracking of IPs, Devices, and their status on the network.

**File storage & Sharing**

* [NetACBackup](https://github.com/allenc125789/NetACBackup.sh): My own BASH script for NAS based backup management and storage on Linux systems.

**Networking**

* [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
* [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
* [FreeDNS](https://freedns.afraid.org): A third party DDNS service to track my home's dynamic public IP.

Most of these services are self hosted and virtualized in a Proxmox environment. My system is like this for a few security based aspects: Self hosted services can reduce the risk of hacks and data-leaks while data is traversing to an off-site location, and possible bad actors from accessing your private files. Virtualized environments reduce cost of needing multiple systems for multiple platforms, and will also increase my overall security by isolation of individual services.

## -Hardware

Currently I have one central server does most of the magic as a Proxmox Hypervisor. 

* GA-78LMT-S2
  * AMD FX(tm)-6300 Six-Core Processor
  * 12GB RAM (1x 8GB DDR3 DIMM 1600 MHz; 1x 4GB DDR3 DIMM 1600 MHz)
  * HDD 1: Toshiba 1TB 7200 RPM SATA 6.0Gb/s Hard Drive
  * HDD 2: Seagate 2TB 5400 RPM SATA 6.0Gb/s Hard Drive 

There are some limitations with this setup, such as the motherboard has no IOMMU support, which makes pass-through of PCI(e) devices impossible for projects such as a GPU passthrough for a gaming VM, or a Network Card passthrough for my virtual router. Another limitation I face is the number of VM's I can safely make without over-use of resources. I'd also be limited to 6 VM's total with 1 core per VM. With these limitations in mind, I can make the most out of my system.

All of my homelab's devices and VM's are listed here, and via the pictures below on the *Devices* (Documentation tracked and logged via Netbox).

**Devices**

My device list via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-52-50.png)

**Virtual Machines**

Some of my virtual machines include: OPNsense, which is acting as a DHCP and DNS server. OPNsense's DNS and DHCP services can interact seamlessly together by automatically logging selected devices. I chose to only register hostnames of Static devices within my DHCP. Other virtual machines include the bitwarden password manager, and my own backup script. Below shows all my virtual machines and the role(s) they have.

Proxmox GUI overview.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2023-08-48.png)

Virtual machine list via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-53-38.png)

## -Network

Designing my network was made extremley easy with Netbox. After determinging the number of devices I have, I decided to go with a /26 subent, as it (1) will allow growth if I decide to add more devices to my network without being too unessesarily large, and (2) helps ease the process of organizing.

**Network Map**

**IP Ranges**

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-49-28.png)

**IP Reservations**

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-51-57.png)

**VLANS**

Work in progress. Will update soon.

**Monitoring**

Work in progress. Will update soon.

## -Automation

**The Linux Shell**

Because most of my machines run linux, using it's built in scheduiling systems made the process of automation very easy. I use the shell job schedueling tool `cron`, for it's easy one line commands.

A `cron` example:



**My Script**

