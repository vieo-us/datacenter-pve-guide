# G003 - Proxmox VE installation

This guide explains how to install a Proxmox VE **8.2.2** platform on the hardware detailed in the [**G001** guide](G001%20-%20Hardware%20setup.md). This procedure follows a straightforward path, configuring only basic parameters. Any advanced configurations will be covered in later guides.

There are a few different ways to install a Proxmox VE platform, and this guide will cover all of them. In some circumstances, you may source Infrastructure as a Service (IaaS) or Metal as a Service (MaaS) from a provider that comes pre-installed with the distribution of your choice. Several providers offer virtualization platforms alongside other distributions such as XCP-NG, ESXi, and Proxmox VE. In these cases, the installation may be pre-configured to varying degrees, depending on the level of access provided by the data center.

Typically, data centers that provide remote KVM access will bootstrap the server with an ISO image over a Preboot Execution Environment (PXE), allowing you to complete the installation via remote KVM. Others may offer a VNC or Spice console for installation completion. In our case, no such options are offered; the installation is delivered fully configured, allowing immediate access to the web GUI via the public IP address on port 8006.

This is not a setback, as the system can be further customized to meet specific use cases. If we need to rescue the system, we can trigger a RescueCD to boot into the server RAM, allowing us to work on a troubled installation without overwriting the hard drives. Additionally, we can trigger a reinstallation of Proxmox VE if it becomes necessary to start over.

But what if we want more control over the initial installation? Without remote KVM or any provider-offered VNC/Spice consoles, we must find alternative installation methods. In the next few guides, we will cover the most common methods of installing Proxmox VE outside of using the standard ISO method. These methods will mitigate the lack of remote KVM, VNC, or Spice access by default. However, a guide on the standard ISO installation method will also be provided.

We have identified and will cover the following installation methods:

- Standard ISO installation
- Installation via SSH, VNC and RescueCD system using Qemu
- Installation via SSH over an installed Debian distribution

The latter two methods will allow remote installation when a pre-configured delivery is not optimal.

## Navigation

[<< Previous (**G002. Network Operations Center**)](G002%20-%20Network%20Operations%20Center.md) | [+Table of Contents+](G000%20-%20Table%20of%20Contents.md) | [Next (**G003. Host configuration 01**) >>](G003%20-%20Host%20configuration%2001%20~%20Apt%20sources%2C%20updates%20and%20extra%20tools.md)
