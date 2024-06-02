# G003 - Proxmox VE installation

This guide explains how to install a Proxmox VE 8.2 platform on the hardware detailed in the [**G001** guide](G001%20-%20Hardware%20setup.md). This procedure follows a straightforward path, configuring only basic parameters. Any advanced configurations will be covered in later guides.

TThere are a few different ways to install a Proxmox VE platform, and this guide will cover all of them. In some circumstances, you may source Infrastructure as a Service (IaaS) or Metal as a Service (MaaS) from a provider that comes pre-installed with the distribution of your choice. Several providers offer virtualization platforms alongside other distributions such as XCP-NG, ESXi, and Proxmox VE. In these cases, the installation may be pre-configured to varying degrees, depending on the level of access provided by the data center.

Typically, data centers that provide remote KVM access will bootstrap the server with an ISO image over a Preboot Execution Environment (PXE), allowing you to complete the installation via remote KVM. Others may offer a VNC or Spice console for installation completion. In our case, no such options are offered; the installation is delivered fully configured, allowing immediate access to the web GUI via the public IP address on port 8006.



## References

### _Proxmox_

- [Proxmox](https://www.proxmox.com/en/)
- [Proxmox VE installation guide](https://pve.proxmox.com/wiki/Installation)
- [Proxmox VE admin guide. Installing Proxmox VE](https://pve.proxmox.com/pve-docs/chapter-pve-installation.html)
- [Proxmox VE. System Requirements](https://www.proxmox.com/en/proxmox-ve/requirements)

### _Rufus_

- [Rufus](https://rufus.ie/)

## Navigation

[<< Previous (**G001. Hardware setup**)](G002%20-%20Hardware%20setup.md) | [+Table Of Contents+](G000%20-%20Table%20Of%20Contents.md) | [Next (**G003. Host configuration 01**) >>](G003%20-%20Host%20configuration%2001%20~%20Apt%20sources%2C%20updates%20and%20extra%20tools.md)
