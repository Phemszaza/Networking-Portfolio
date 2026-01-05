# Bank Network Design and Implementation

## 📖 Project Overview
This project presents the design and implementation of a scalable and secure **Bank Enterprise Network** using Cisco Packet Tracer. The network is designed to support multiple departments across different floors with redundancy, inter-VLAN routing, dynamic IP allocation, and fault tolerance.

The project demonstrates real-world enterprise networking concepts including VLAN segmentation, Layer 3 switching, OSPF routing, DHCP relay, and gateway redundancy using HSRP.

---

## 🏦 Network Requirements
- Multiple departments distributed across four floors
- Each department placed in a separate VLAN
- Inter-VLAN routing using Layer 3 switches
- Centralized DHCP server
- Dynamic routing using OSPF
- Redundant default gateways using HSRP
- Secure trunking between switches
- High availability between core and distribution layers

---

## 🧱 Network Architecture
- **Access Layer:** End devices connected to access switches
- **Distribution Layer:** Layer 3 switches performing inter-VLAN routing
- **Core Layer:** Redundant core routers providing routing between floors
- **Services Layer:** Central DHCP and server infrastructure

---

## 🗂 VLAN Design
| VLAN ID | Department     | Subnet            |
|---------|----------------|-------------------|
| 10      | Management     | 192.168.10.0/26   |
| 20      | Research       | 192.168.10.64/26  |
| 30      | HR             | 192.168.10.128/26 |
| 40      | Marketing      | 192.168.10.192/26 |
| 50      | Accounting     | 192.168.11.0/26   |
| 60      | Finance        | 192.168.11.64/26  |
| 70      | Logistics      | 192.168.11.128/26 |
| 80      | Customer       | 192.168.11.192/26 |
| 90      | Guest          | 192.168.12.0/26   |
| 100     | Admin          | 192.168.12.64/26  |
| 110     | IT             | 192.168.12.128/26 |
| 120     | Servers        | 192.168.12.192/26 |

---

## 🔁 Routing Design
- OSPF is used as the interior gateway protocol
- All Layer 3 switches participate in OSPF Area 0
- Point-to-point /30 networks used between core and distribution layers
- Dynamic route advertisement ensures full inter-floor connectivity

---

## 🔐 Redundancy and High Availability
- HSRP configured on VLAN interfaces
- Virtual gateway IP used by end devices
- Active and standby roles split across floors
- Ensures uninterrupted connectivity during device failure

---

## 🌐 DHCP Design
- Central DHCP server located on Floor 4
- DHCP relay configured using `ip helper-address`
- Each VLAN forwards DHCP requests to the server
- Dynamic IP assignment across all departments

---

## 🧪 Testing and Validation
- Successful inter-VLAN communication
- End-to-end connectivity across all floors
- DHCP address assignment verified
- OSPF neighbor adjacencies confirmed
- Redundancy tested by interface shutdown

---

## 🛠 Tools Used
- Cisco Packet Tracer
- Layer 3 Switches
- Cisco Routers
- VLANs, OSPF, DHCP, HSRP

---

## 📁 Files Included
- Packet Tracer topology file
- IP addressing documentation
- Routing and VLAN design documentation
- Network diagrams

---

## 👤 Author
Oluwafemi Gabriel
Aspiring Network Engineer  
