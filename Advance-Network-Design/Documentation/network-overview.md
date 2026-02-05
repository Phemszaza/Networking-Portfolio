# Network Topology Overview

## Architecture Summary
The enterprise network is designed using a hierarchical campus model consisting of Internet, Perimeter, Core, Distribution, 
and Access layers. The design focuses on high availability, security, scalability, and ease of management.

## Internet and ISP Connectivity
The network connects to two Internet Service Providers to ensure redundancy and fault tolerance. Public IP addressing uses /30 point-to-point subnets for efficiency and security.

## Perimeter Security
Two firewalls are deployed in a redundant configuration. The firewall design includes three security zones:
- Outside zone for internet-facing interfaces
- Inside zone for internal corporate users
- DMZ zone for public-facing services

The DMZ hosts services such as Web, Email, Application, and NAS servers using static IP addressing.

## Core Layer
The core layer consists of two high-performance switches interconnected using EtherChannel with LACP. HSRP is configured to provide gateway redundancy for downstream networks. OSPF is used as the internal routing protocol.

## Access and Distribution Layer
Each floor is equipped with a Layer 3 switch that performs inter-VLAN routing locally. VLANs are created per department to enforce network segmentation and security boundaries.

## Services
- DHCP is centrally located and accessed via IP helper addresses
- DNS and internal services reside in the inside security zone
- Guest VLANs are isolated using access control policies

## Wireless and Voice
Wireless connectivity is managed centrally using a Wireless LAN Controller. Lightweight Access Points are deployed across all floors. VoIP services are supported using dedicated voice VLANs and a voice controller.

## High Availability Features
- Dual ISPs
- Dual firewalls
- HSRP on all user VLANs
- EtherChannel between core switches
- OSPF dynamic routing
