# G002 - Network Operations Center (NOC)

Our cluster is deployed within the NOCIX data center, located in Kansas City, Missouri. NOCIX offers a robust and secure environment for hosting dedicated and virtual servers. Known for its affordability and reliability, NOCIX specializes in providing budget-friendly solutions for mission-critical hosting needs.

We chose NOCIX for its central location within the United States. Being in the middle of the country allows for decent latency from other parts of the country, as the mileage between distant points remains almost the same on each side. This ensures that all points receive consistent latency relative to their distance.

## Key Features:

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

## Summary

This hardware setup provides a comprehensive and scalable cluster environment for deploying a Virtual Data Center using Proxmox VE. The NOCIX data center enhances this setup with affordability with high reliability, robust security measures, redundant power infrastructure, reliable network capabilities, and extensive peering arrangements ensures a stable and secure environment for hosting enterprise-grade workloads.

## References

### _Hardware_

- [NOCIX](https://www.nocix.net/)
- [1530 Swift Data-Center](https://1530swift.com/)

## Navigation

[<< Previous (**G001** - Hardware Setup) >>](G001%20-%20Hardware%20Setup.md) | [+Table of Contents+](G000%20-%20Table%20of%20Contents.md) | [Next (**G003. Proxmox VE installation**) >>](G003%20-%20Proxmox%20VE%20installation.md)