# IP Addressing Plan

## Private Addressing
All internal networks use RFC 1918 private IP address space.

### User VLAN Subnets
| VLAN | Department    | Network       | Mask|
|------|---------------|---------------|-----|
| 10   | Management    | 192.168.10.0  | /24 |
| 20   | LAN(USER)     | 172.16.0.0    | /16 |
| 50   | WLAN          | 10.20.0.0     | /16 |
| 70   | VOIP          | 172.30.0.0    | /16 |
| 90   | INSIDE SERVER | 10.11.11.32   | /27 |
| 199  | BLACKHOLE     |   -           | -   |
| -    | DMZ           | 10.11.11.0    | /27 |

## Point-to-Point Links
All inter-device links use /30 networks to minimize IP waste.

| Department    | Network       | Mask| PORTS            |
|---------------|---------------|-----|------------------|
| CORESW1- FW1  | 10.2.2.0      | /30 |Gig1/0/1 - Gig1/3
| CORESW1- FW2  | 10.2.2.4      | /30 |Gig1/0/2 - Gig1/3
| CORESW2- FW1  | 10.2.2.8      | /30 |Gig1/0/2 - Gig1/4
| CORESW2- FW2  | 10.2.2.12     | /30 |Gig1/0/1 - Gig1/4
| SEACOMISP- FW1| 105.100.50.0  | /30 |Gig/0/0 - Gig1/1
| SEACOMISP- FW2| 105.100.50.4  | /30 |Gig0/1 - Gig1/1
| SAFACOMISP-FW1| 197.200.100.0 | /30 |Gig0/0 - Gig1/2
| SAFACOMISP-FW2| 197.200.100.4 | /30 |Gig0/1 - Gig1/2
| SEACOMISP-INTERNET| 20.20.20.0  | /30 |Gig0/2 - Gig0/0
| SAFACOMISP-INTERNET| 30.30.30.0 | /30 |Gig0/2 - Gig0/1
