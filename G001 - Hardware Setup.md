# G001 - Hardware Setup

This section provides detailed specifications and setup instructions for the servers used in deploying a Virtual Data Center (VDC) with Proxmox VE 8.2.2. The following hardware has been selected and configured to ensure a robust and scalable environment capable of handling a variety of enterprise-grade workloads.

The first requirement is to have several capable servers. As mentioned in the [README](README.md), affordable enterprise-grade computers are recommended, which means that the latest and fastest machines are not necessary. Any relatively modern server could be adequate, but it must meet certain minimum requirements to effectively scale the workloads described in this guide series.

## Server Specifications

The deployment consists of a mix of powerful servers with high core counts, substantial memory, and SSD storage to ensure performance and reliability.

### WireGuard Server

- **Processor**: Dual Xeon 5160 @ 3.00GHz (4 Cores / 4 Threads)
- **Memory**: 16GB DDR2 RAM
- **Storage**:
  - 120GB SSD
  - 2 x 500GB SSD

### PVE Node 1

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 4TB SSD

### PVE Node 2

- **Processor**: Dual Xeon E5-2683 v4 @ 2.10GHz / 3.0GHz Turbo (32 Cores / 64 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 960GB SSD
  - 8TB SATA

### PVE Node 3

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 2TB SSD

### PVE Node 4

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 1TB SSD

## Network Configuration

Each server is equipped with a /29 subnet providing 5 usable IPv4 addresses, plus an additional /28 subnet for each PVE node, yielding 13 usable IPv4 addresses per node. This results in a total of 77 public IPv4 addresses. Additionally, each server is assigned a /64 IPv6 subnet. The total cluster resources include 72 usable IPv4 address, 4 x /64 IPv6 subnets, 280 CPUs and 512GB of RAM, with storage totaling approximately 24TB.

For optimal performance, a 10Gbit Ethernet connection is recommended for the network configuration. However, in this preconfigured setup, 1Gbit Ethernet connections to the Network Operations Center (NOC) are being used.

## Storage Overview

The total storage capacity across all nodes is approximately 24TB, distributed as follows:

- **WireGuard Server**: 1.12TB (120GB SSD + 2 x 500GB SSD)
- **PVE Node 1**: 8TB (2 x 4TB SSD)
- **PVE Node 2**: 8.96TB (960GB SSD + 8TB SATA)
- **PVE Node 3**: 4TB (2 x 2TB SSD)
- **PVE Node 4**: 2TB (2 x 1TB SSD)

## References

### _Hardware_

- [Intel Xeon 5160](https://ark.intel.com/content/www/us/en/ark/products/27219/intel-xeon-processor-5160-4m-cache-3-00-ghz-1333-mhz-fsb.html)
- [Intel Xeon E5-2696 V3](https://www.techpowerup.com/cpu-specs/xeon-e5-2696-v3.c2903)
- [Intel® Xeon E5-2683 V4](https://www.intel.com/content/www/us/en/products/sku/91766/intel-xeon-processor-e52683-v4-40m-cache-2-10-ghz/specifications.html)

## Navigation

[<< Previous (**README**)](README.md) | [+Table of Contents+](G000%20-%20Table%20of%20Contents.md) | [Next (**G002. Network Operations Center**) >>](G002%20-%20Network%20Operations%20Center.md)
