# Cisco Packet Tracer Projects

This repository contains two networking projects developed using Cisco Packet Tracer. These projects not only simulate real-world scenarios but also demonstrate critical networking concepts including IP addressing, complete subnetting, VLAN configuration, inter-VLAN routing, DHCP implementation, and wireless connectivity.

---

## Problem Statement 1: ACCOUNTS and DELIVERY Departments Network

### Objective
Design a network in Cisco Packet Tracer to connect the ACCOUNTS and DELIVERY departments.

### Requirements
- Each department must have at least 2 PCs.
- Use appropriate switches and routers.
- All interfaces must be configured using the network address **192.168.40.0** with correct IP addresses, subnet masks, and gateways.
- Devices must be connected using proper cables.
- PCs in the DELIVERY department must be able to ping PCs in the ACCOUNTS department.

### Complete Subnetting Details (Project 1)
For this project, we used a single subnet derived from the base network **192.168.40.0/24**:
- **Network ID:** 192.168.40.0  
- **Subnet Mask:** 255.255.255.0  
- **Broadcast Address:** 192.168.40.255  
- **Available Host Range:** 192.168.40.1 to 192.168.40.254

This subnet provides sufficient IP addresses for all devices in both departments. No further subdivision was required since the entire network operates in one broadcast domain.

### Implementation and Concepts
- **IP Addressing:** Each PC was assigned a unique IP within the 192.168.40.0/24 range.
- **Default Gateway:** The router interface was configured as the default gateway (e.g., 192.168.40.1).
- **Connectivity Testing:** After proper cabling and device interconnection, connectivity was verified by pinging between PCs in the ACCOUNTS and DELIVERY departments.
- **Physical Cabling and Device Interconnection:** Appropriate cables (copper straight-through) were used to connect PCs, switches, and the router.

---

## Problem Statement 2: XYZ Company Branch Network

### Objective
Design a separate branch network for XYZ Company’s new branch in Bonalbo, ensuring isolation from the headquarters network.

### Requirements
- Use one Cisco router and one Cisco switch.
- Create 3 departments: Admin/IT, Finance/HR, and Customer Service/Reception, each in its own VLAN.
- Provide wireless connectivity for users in each department.
- Devices must obtain IP addresses automatically via DHCP.
- All departments should be able to communicate with each other.

### Complete Subnetting Details (Project 2)
Given the ISP base network **192.168.1.0/24**, we divided it into three subnets using a /26 mask (which provides 64 addresses per subnet):

#### Subnet for VLAN 1 (Admin/IT)
- **Network ID:** 192.168.1.0  
- **Subnet Mask:** 255.255.255.192  
- **Broadcast Address:** 192.168.1.63  
- **Available Host Range:** 192.168.1.1 to 192.168.1.62

#### Subnet for VLAN 2 (Finance/HR)
- **Network ID:** 192.168.1.64  
- **Subnet Mask:** 255.255.255.192  
- **Broadcast Address:** 192.168.1.127  
- **Available Host Range:** 192.168.1.65 to 192.168.1.126

#### Subnet for VLAN 3 (Customer Service/Reception)
- **Network ID:** 192.168.1.128  
- **Subnet Mask:** 255.255.255.192  
- **Broadcast Address:** 192.168.1.191  
- **Available Host Range:** 192.168.1.129 to 192.168.1.190

These subnets were carefully planned to ensure that each department has its own IP space, and that the router can perform inter-VLAN routing between them.

### Implementation and Concepts
- **VLAN Configuration:** VLANs were created on the switch to logically separate the departments.
- **Inter-VLAN Routing:** A router-on-a-stick setup was implemented. Subinterfaces (e.g., Gig0/0.10, Gig0/0.20, Gig0/0.30) were configured on the router, each assigned an IP address corresponding to the gateway of its respective VLAN.
- **DHCP Configuration:** DHCP was set up on the router (or on a dedicated DHCP server) to dynamically assign IP addresses from each subnet to wired and wireless devices.
- **Wireless Integration:** Wireless Access Points were deployed to provide wireless connectivity, with DHCP ensuring seamless IP assignment.
- **Testing Connectivity:** The inter-VLAN routing and DHCP functionality were validated by verifying that devices from all VLANs could communicate with each other using ping tests.

---

## How to Use the Projects
1. **Download** the Packet Tracer (.pkt) files from this repository.
2. **Open** the files in Cisco Packet Tracer.
3. **Review** the network topologies, VLAN configurations, and DHCP setups.
4. **Run** simulation mode to observe IP assignment, inter-VLAN routing, and end-to-end connectivity.

### Files Included
- `Problem1_ACCOUNTS_DELIVERY.pkt`
- `Problem2_XYZ_BRANCH.pkt`

---

## Conclusion
These projects combine both fundamental and advanced networking concepts. In Problem Statement 1, we reinforced proper IP addressing, subnetting, and connectivity within a single subnet environment. In Problem Statement 2, we applied complete subnetting techniques to divide a base network into multiple subnets, implemented VLAN segmentation, and configured inter-VLAN routing along with DHCP and wireless connectivity. Together, these projects have deepened our understanding of network design, implementation, and troubleshooting, providing practical insights into designing professional-grade networks using Cisco technologies.

Made with Cisco Packet Tracer.
