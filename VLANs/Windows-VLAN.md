
## Description

Windows based segment of the network. These servers are administrated remotely by using the **Server Manager** and **Admin Center** via the domain controller, *home-ok-ws01p* on a personally created domain admin account.

## VLAN 2, Windows (192.168.0.100 - 149)

- Hostname: *home-ok-ws01p*
  - **Windows Server 2016**: running Windows Admin Center, Active Directory and DNS roles.
>
- Hostname: *home-ok-de02p*
  - **Windows 11 (Desktop)**: for general Administration.
>
- Hostname: *home-ok-hv02p*
  - **Windows Server Core 2016**: Windows Admin Center and running Hyper-V.
> *Virtual Machines --> home-ok-hv02p*
- Hostname: *home-ok-na03p*
  - **Debian 12**: second server running my application, TurtleNAS.
