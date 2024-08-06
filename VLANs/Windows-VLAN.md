
## Description

Windows based segment of the network. These servers are administrated remotely by using the **Server Manager** and **Admin Center** via the domain controller, `home-ok-ws01p` on a personally created domain admin account (**Kerberos** authentication used). All computers (minus the one Linux Virtual Machine) on the network are connected to the turtlenas.com domain.

## 🪟 VLAN 2, Windows (192.168.0.100 - 149)/24

- Model: Dell | PowerEdge T310
- Hostname: `home-ok-ws01p`
  - **Windows Server 2016**: Gateway for other Windows computers on the domain. running Windows Admin Center, Active Directory and DNS roles.
>
- Model: Lenovo | X220 Tablet Laptop
- Hostname: `home-ok-de02p`
  - **Windows 11 (Desktop)**: for general Administration.
>
- Model: Lenovo | ThinkPad T510
- Hostname: `home-ok-hv02p`
  - **Windows Server Core 2016**: Running Windows Admin Center and Hyper-V.
> *Virtual Machines --> home-ok-hv02p*
- Hostname: `home-ok-na03p`
  - **Debian 12**: second server running my a web server with my application, TurtleNAS, for external access by guests with allowed access.
______________________________________________________________________________

## Gateway View

![Image of Windows Admin Center on home-ok-ws01p](https://github.com/allenc125789/Homelab/blob/main/images/Screenshot%20from%202024-08-05%2022-10-41.png)

______________________________________________________________________________

[Return to Homelab mainpage.](https://github.com/allenc125789/Homelab#lan-19216801---924)
