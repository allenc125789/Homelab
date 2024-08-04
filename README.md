# Homelab

**Description**

Network plan, and organization of my home network. I've designed my network with 2 isolated segments, seperated by VLANs. One mostly containing Windows devices, and the other containing Linux devices. The goal of this design was to deploy Windows and Linux dominated networks, and expirement under them independintly without confliction.

______________________________________________________________________________________________________________________________________________________________________________

# LAN

home-ok-ro01p
* [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.


# Linux VLAN

home-ok-hv01p
* [Proxmox](https://www.proxmox.com/en/): A KVM based Debian hypervisor. 

home-ok-ro02p
* [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.

home-ok-bw01p
* [Bitwarden](https://github.com/bitwarden/server): A self-hosted password manager and vault.

home-ok-na01p
* [TurtleNAS](https://github.com/allenc125789/TurtleNAS): My own application that i'm building, that acts as NAS software for Debian.


Most of these services are self hosted and virtualized in a Proxmox environment. My system are like this for a few security based aspects: Self hosted services can reduce the risk of hacks and data-leaks while data is traversing to an off-site location, and possible bad actors from accessing your private files. Virtualized environments reduce cost of needing multiple systems for multiple platforms, and will also increase my overall security by isolation of individual services.

My OpenVPN however, is run from my physical router ("home-ok-ro01p"). I experiemented running my own OpenVPN server, however I had trouble getting the configuration files syntaxed properly. The default configuration that came packaged in my physical router worked on first try. I continue to use this setup for convienience, but will be studying the file configuration that works so I can set up my own in the future.

## 1b. Hardware

Currently I have one central server does most of the magic as a Proxmox Hypervisor. 

* GA-78LMT-S2
  * AMD FX(tm)-6300 Six-Core Processor
  * 12GB RAM (1x 8GB DDR3 DIMM 1600 MHz; 1x 4GB DDR3 DIMM 1600 MHz)
  * HDD 1: Toshiba 1TB 7200 RPM SATA 6.0Gb/s Hard Drive
  * HDD 2: Seagate 2TB 5400 RPM SATA 6.0Gb/s Hard Drive 

There are some limitations with this setup, such as the motherboard has no IOMMU support, which makes pass-through of PCI(e) devices impossible for projects such as a GPU passthrough for a gaming VM, or a Network Card passthrough for my virtual router. Another limitation I face is the number of VM's I can safely make without over-use of resources. I'd be limited to 6 VM's total with 1 core per VM. With these limitations in mind however, I can make the most out of my system.

All of my homelab's devices and VM's are listed here, and via the pictures below on the *Devices* (Documentation tracked and logged via Netbox).

**Devices**


**Virtual Machines**

Some of my virtual machines include: OPNsense, which is acting as a DHCP and DNS server. OPNsense's DNS and DHCP services can interact seamlessly together by automatically logging selected devices. I chose to only register hostnames of Static devices within my DHCP. Other virtual machines include the bitwarden password manager, and my own backup script. Below shows all my virtual machines and the role(s) they have.

Proxmox GUI overview.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2023-08-48.png)

Virtual machine list via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-53-38.png)

## 1c. Network

Designing my network was made extremley easy with Netbox. After determinging the number of devices I have, I decided to go with a /26 subent, as it (1) will allow growth if I decide to add more devices to my network without being too unessesarily large, and (2) helps ease the process of organizing.

**Network Map**

**IP Ranges**



