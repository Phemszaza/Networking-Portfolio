# Campus Network Design – Albion University

## Overview
This project presents the design and implementation of a campus network for Albion University using Cisco Packet Tracer.  
The network was designed based on a real-world university scenario with multiple campuses, faculties, buildings, and shared services.

The goal of the project is to provide secure, scalable, and reliable network connectivity between staff, students, internal servers, and an external cloud-based email server.

---

## Project Scenario
Albion University is a large university with two campuses located approximately 20 miles apart.  
The university consists of four main faculties:
- Health and Sciences
- Business
- Engineering and Computing
- Art and Design

Both staff and students require reliable network access, with staff using dedicated PCs and students accessing shared lab systems.

---

## Network Requirements
The design was developed to meet the following requirements:

### Main Campus
- **Building A**
  - Administrative departments: Management, HR, Finance
  - Faculty of Business
  - Shared networking infrastructure using VLAN segmentation
- **Building B**
  - Faculty of Engineering and Computing
  - Faculty of Art and Design
- **Building C**
  - Student laboratories
  - IT Department
  - Internal servers including the University Web Server

### Smaller Campus
- Faculty of Health and Sciences
- Staff offices and student laboratories located on separate floors

### External Services
- An email server hosted externally in the cloud
- Static routing used to reach the external server

---

## Network Design and Technologies Used
- VLANs implemented to separate departments and faculties
- Each department assigned to its own IP subnet
- Inter-VLAN routing configured on routing devices
- RIPv2 used for internal dynamic routing
- Static routing configured for external cloud connectivity
- Router-based DHCP used to assign dynamic IP addresses in Building A
- Switch security features applied where appropriate

---

## Implementation
The network topology and configurations were implemented and tested in Cisco Packet Tracer.  
End-to-end connectivity was verified between:
- Different VLANs
- Main campus and remote campus
- Internal servers
- External cloud-based email server

---

## Files Included
- Cisco Packet Tracer project file (`.pkt`)
- Network documentation
- IP addressing plan
- Routing and VLAN design explanations
- Test results and verification

---

## Tools Used
- Cisco Packet Tracer
- GitHub for documentation and version control

---

## Author Oluwafemi Gabriel
This project was designed and implemented as part of a networking portfolio to demonstrate practical skills in campus network design and configuration.
