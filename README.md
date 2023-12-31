# Homelab

**Goal**

My goals for this project as my first homelab was to get all my data organized, implement new technology to increase my home network's security and functionality, and create an automated system with reproduceable backups.

**Description**

As a part of my homelab, for the documentation I want to upload it to github for future reproduction, organization and planning. I've outlined the various aspects of my project which utilizes many Open Source solutions to create a secure, lightweight (*and very cost effective!*) user space. This project introduced me to a lot of new tools and getting a deeper understanding of networking services and their coexisting nature within the OSI Model. I just recently finished utilizing my central server to near 100% of it's resources, and near ready to start planning an upgrade on my infrastructure. This Repo will contain: 

1. [What I Have.](https://github.com/allenc125789/Homelab/blob/main/README.md#awhat-i-have)

  - 1a. [Hosted Services & Software](https://github.com/allenc125789/Homelab/blob/main/README.md#1a-hosted-services--software)
  - 1b. [Hardware](https://github.com/allenc125789/Homelab/blob/main/README.md#1b-hardware)
  - 1c. [Network](https://github.com/allenc125789/Homelab/blob/main/README.md#1c-network)
  - 1d. [Automation](https://github.com/allenc125789/Homelab/blob/main/README.md#1d-automation)

2. [What is my Fail-Safe?](https://github.com/allenc125789/Homelab/blob/main/README.md#2-what-is-my-fail-safe)

3. [What comes next?](https://github.com/allenc125789/Homelab/blob/main/README.md#3-what-comes-next)

______________________________________________________________________________________________________________________________________________________________________________

# 1. What I Have.

## 1a. Hosted Services & Software

**Server Management**

* [Bitwarden](https://github.com/bitwarden/server): A self-hosted password manager and vault.
* [Proxmox](https://www.proxmox.com/en/): A KVM based Debian hypervisor. 
* [Netbox](https://github.com/netbox-community/netbox): A Network documentation program. Allows the logging of IPs, Devices, and their status on the network.

**File storage & Sharing**

* [NetACBackup](https://github.com/allenc125789/NetACBackup.sh): My own BASH script for NAS based backup management and storage on Linux systems.

**Networking**

* [OPNsense](https://opnsense.org/): Open source router software acting as a DHCP and DNS server.
* [OpenVPN](https://github.com/OpenVPN/openvpn): Self-hosted VPN.
* [FreeDNS](https://freedns.afraid.org): A third party DDNS service to track my home's dynamic public IP.

Most of these services are self hosted and virtualized in a Proxmox environment. My system is like this for a few security based aspects: Self hosted services can reduce the risk of hacks and data-leaks while data is traversing to an off-site location, and possible bad actors from accessing your private files. Virtualized environments reduce cost of needing multiple systems for multiple platforms, and will also increase my overall security by isolation of individual services.

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

My device list via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-52-50.png)

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

Provided via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-49-28.png)

**IP Reservations**

Provided via netbox.

![](https://github.com/allenc125789/Homelab/blob/main/img-files/Screenshot%20from%202023-10-23%2022-51-57.png)

**VLANS**

Work in progress. Will update soon.

**Monitoring**

Work in progress. Will update soon.

## 1d. Automation

**The Linux Shell**

Because most of my machines run linux, using it's built in schedueling systems made the process of automation very easy. I use the shell job schedueling tool `cron`, for it's easy one line commands.

A `cron` example on my Bitwarden virtual machine (runs Debian for the OS):

```
SHELL=/bin/bash
0 23 */2 * * rm -r /home/bitwarden/bwbackups/* && cp -r /home/bitwarden/bwdata /home/bitwarden/bwbackups && chown -R bitwarden:bitwarden /home/bitwarden/bwbackups
```
This code, in order: `SHELL=/bin/bash` Sets the shell for the cron job (default is SH, I want BASH for better functionality.), I then set the time frame for when to run the script `0 23 */2 * *`, which translates to "Every 2 days at 11pm", `rm -r /home/bitwarden/bwbackups/*` to remove old backup files, `cp -r /home/bitwarden/bwdata /home/bitwarden/bwbackups` to copy any new changes to the backup folder, and finally I set permissions with `chown -R bitwarden:bitwarden /home/bitwarden/bwbackups`, as the default permissions make it difficult for the non-root user to copy any meaningful data during my NAS's backup process.

**My Script**

I created a BASH script as a seperate project from my homelab, but has since become an essential tool in how I like to store data. What my script does is it uses standard shell commands from linux to create a UI that helps manage `rsync` in a streamlined manner to archive and encrypt data for multiple remote users/devices. It can be run without user interaction after its initial configuration. Combined with the pre mentioned `cron` tool, I have it automated on my NAS to backup my network every week, on Sunday at 1am. It's made my life adminstrating my network very easy and was a great learning experience!

My script can be found in my github profile, and in the link [here](https://github.com/allenc125789/NetACBackup.sh/tree/main).

# 2. What is my Fail-Safe?

My Fail-Safe follows the 3-2-1 Backup prodecure. 3 backups, on 2 drives, with 1 off-site. Most of the work is done by my own BASH Script which copies, compresses, and encrypts all necessary data at a file level, which I can then distribute to seperate drives. 2 HDDs on my central server and a thumb-drive I occasionally update, kept in a secure location at my close family's house.

This process let's me edit data without worries, and in the event of a natural disaster or possible data corruption, I have the thumbdrive at my family's house, which is located a city away.

# 3. What comes next?

