# Network Overview

## Design Model
The network follows a hierarchical enterprise design:
- Core Layer
- Distribution Layer
- Access Layer
- Edge Layer (Internet)

## Core Layer
- CORE-SW1
- CORE-SW2
  
Provides high-speed routing and redundancy.

## Distribution Layer
- DIST-SW1
- DIST-SW2
  
Aggregates access layer switches and performs inter-VLAN routing.

## Edge Layer
- EDGE-R1 connected to ISP-1
- EDGE-R2 connected to ISP-2
  
Performs NAT and Internet access.

## Access Layer FLOOR 1 SWITCH
- User PCs
- IP Phones
- Printers
- Guest WiFi
