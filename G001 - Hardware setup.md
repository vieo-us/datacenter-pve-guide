# G001 - Hardware Setup

This section provides detailed specifications and setup instructions for the servers used in deploying a Virtual Data Center (VDC) with Proxmox VE 8.2.2. The following hardware has been selected and configured to ensure a robust and scalable environment capable of handling a variety of enterprise-grade workloads.

The first requirement is to have several capable servers. As mentioned in the [README](README.md), affordable enterprise-grade computers are recommended, which means that the latest and fastest machines are not necessary. Any relatively modern server could be adequate, but it must meet certain minimum requirements to effectively scale the workloads described in this guide series.

## Server Specifications

The deployment consists of a mix of powerful servers with high core counts, substantial memory, and SSD storage to ensure performance and reliability.

#### WireGuard Server

- **Processor**: Dual Xeon 5160 @ 3.00GHz (4 Cores / 4 Threads)
- **Memory**: 16GB DDR2 RAM
- **Storage**:
  - 120GB SSD
  - 2 x 500GB SSD

#### PVE Node 1

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 4TB SSD

#### PVE Node 2

- **Processor**: Dual Xeon E5-2683 v4 @ 2.10GHz / 3.0GHz Turbo (32 Cores / 64 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 960GB SSD
  - 8TB SATA

#### PVE Node 3

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 2TB SSD

#### PVE Node 4

- **Processor**: Dual Xeon E5-2696 v3 @ 2.30GHz / 3.6GHz Turbo (36 Cores / 72 Threads)
- **Memory**: 128GB DDR4 RAM
- **Storage**:
  - 2 x 1TB SSD

### Network Configuration

Each server is equipped with a /29 subnet providing 5 usable IPv4 addresses, plus an additional /28 subnet for each PVE node, yielding 13 usable IPv4 addresses per node. This results in a total of 77 public IPv4 addresses. Additionally, each server is assigned a /64 IPv6 subnet. The total cluster resources include 72 usable IPv4 address, 4 x /64 IPv6 subnets, 280 CPUs and 512GB of RAM, with storage totaling approximately 24TB.

For optimal performance, a 10Gbit Ethernet connection is recommended for the network configuration. However, in this preconfigured setup, 1Gbit Ethernet connections to the Network Operations Center (NOC) are being used.

### Storage Overview

The total storage capacity across all nodes is approximately 24TB, distributed as follows:

- **WireGuard Server**: 1.12TB (120GB SSD + 2 x 500GB SSD)
- **PVE Node 1**: 8TB (2 x 4TB SSD)
- **PVE Node 2**: 8.96TB (960GB SSD + 8TB SATA)
- **PVE Node 3**: 4TB (2 x 2TB SSD)
- **PVE Node 4**: 2TB (2 x 1TB SSD)

## Network Operations Center (NOC) Specifications

Our cluster is deployed within the NOCIX data center, located in Kansas City, Missouri. NOCIX offers a robust and secure environment for hosting dedicated and virtual servers. Known for its affordability and reliability, NOCIX specializes in providing budget-friendly solutions for mission-critical hosting needs.

We chose NOCIX for its central location within the United States. Being in the middle of the country allows for decent latency from other parts of the country, as the mileage between distant points remains almost the same on each side. This ensures that all points receive consistent latency relative to their distance.

#### Key Features:

1. **Security**:
    - Access within the facility is controlled by biometric systems, including mantraps and blast-proof corridors.
    - Extensive video surveillance covers every row of the dedicated server facility and the building exteriors, with video recordings maintained for security purposes.
    - An armed staff member ensures additional safety within the facility.

2. **Power Infrastructure**:
    - The data center is fed by dual power grids from separate substations, ensuring high redundancy.
    - Temporary power is supplied by N+1 redundant UPS systems, which allow maintenance without power interruption.
    - Onsite backup power is provided by both natural gas and diesel generators, capable of running for 48 hours without refueling. Contracts with local fuel suppliers ensure continuous power availability even during extended outages.

3. **Network Capabilities**:
    - NOCIX operates a self-healing, private fiber ring connecting to downtown Kansas City, providing high network reliability.
    - The network supports both IPv4 and IPv6, facilitating modern internet connectivity requirements.
    - Despite the recommendation of 10GB Ethernet for optimal performance, the facility supports 1GB Ethernet connections, which can be upgraded as necessary to meet increasing demands.

4. **Peering and Connectivity**:
    - NOCIX has extensive peering arrangements to ensure high-speed connectivity and redundancy. The facility is connected to multiple Tier 1 carriers and internet exchanges, enhancing both local and global reach.
    - This extensive peering ensures low latency and high availability, which is crucial for maintaining consistent performance and reliability for hosted services.

5. **Service Offerings**:
    - NOCIX offers instant activation for some preconfigured server plans and custom server configurations ready within two business days.
    - All servers come with full root SSH access, free setup, and competitive pricing.
    - The facility provides a range of dedicated server options, from budget-friendly to high-performance configurations, suitable for various business needs.

### Summary

This hardware setup provides a comprehensive and scalable cluster environment for deploying a Virtual Data Center using Proxmox VE. The NOCIX data center enhances this setup with affordability with high reliability, robust security measures, redundant power infrastructure, reliable network capabilities, and extensive peering arrangements ensures a stable and secure environment for hosting enterprise-grade workloads.

## References

### _Hardware_

- [Intel Xeon 5160](https://ark.intel.com/content/www/us/en/ark/products/27219/intel-xeon-processor-5160-4m-cache-3-00-ghz-1333-mhz-fsb.html)
- [Intel Xeon E5-2696 V3](https://www.techpowerup.com/cpu-specs/xeon-e5-2696-v3.c2903)
- [Intel® Xeon E5-2683 V4](https://www.intel.com/content/www/us/en/products/sku/91766/intel-xeon-processor-e52683-v4-40m-cache-2-10-ghz/specifications.html)
- [NOCIX](https://www.nocix.net/)
- [1530 Swift Data-Center](https://1530swift.com/)

## Navigation

[<< Previous (**README**)](README.md) | [+Table Of Contents+](G000%20-%20Table%20Of%20Contents.md) | [Next (**G002. Proxmox VE installation**) >>](G002%20-%20Proxmox%20VE%20installation.md)
