# Advance Network Design and Implementation

## Project Overview
This project presents the design and implementation of a secure, redundant enterprise campus network for a multi-floor organization. 
The network was built based on real world enterprise requirements including segmentation, high availability, routing, security zones, and centralized services.

The design follows a hierarchical enterprise model and was implemented using Cisco Packet Tracer.

## Business Scenario
Milkman Innovation Ltd is expanding into a new multi-floor building hosting over 600 staff across multiple departments. The organization requires a secure, scalable, and highly available network infrastructure that supports:

- Wired and wireless users
- Centralized services such as DHCP, DNS, and Active Directory
- Secure DMZ hosting public facing services
- Redundant internet connectivity
- High availability at Layer 3 using HSRP

## Key Technologies Used
- VLANs and Inter-VLAN Routing
- OSPF dynamic routing
- HSRP for gateway redundancy
- Cisco ASA firewall with Inside, Outside, and DMZ zones
- EtherChannel with LACP
- STP with PortFast and BPDU Guard
- DHCP relay using IP helper addresses
- Wireless LAN Controller architecture
- VoIP integration
- Enterprise subnetting and IP planning

## Tools
- Cisco Packet Tracer
- Markdown documentation
- GitHub for version control and portfolio hosting

## Repository Contents
- Packet Tracer topology file
- Logical network diagrams
- Detailed IP addressing and VLAN plans
- Routing and redundancy documentation
- Security design and firewall zoning
- Testing and validation results

## How to Use
1. Open the `.pkt` file using Cisco Packet Tracer
2. Review documentation inside the `Documentation` folder
3. Examine configuration snippets for key devices
