# IP Addressing Plan

## Internal VLANs
| VLAN | Purpose        | Subnet          |
|------|--------------------------|-----------------|
| 10   | Corporate Data (users)   | 10.10.10.0/24   |
| 20   | Voice(IP phones)         | 10.10.20.0/24   |
| 30   | Printers                 | 10.10.30.0/24   |
| 40   | Corporate Wi-Fi          | 10.10.40.0/24   |
| 50   | Guest Wi-Fi              | 10.10.50.0/24   |
| 70   | Servers                  | 10.10.70.0/24   |
| 90   | Voice Services           | 10.10.90.0/24   |
| 99   | Management               | 10.10.99.0/24   |

## Point-to-Point Links
| Link                | Subnet |
|---------------------|---------------|
| Core-SW1 – Core-SW2 | 10.255.0.0/30 |
| Core-SW1 – Dist-sw1 | 10.255.1.0/30 |
| Core-SW1 – Dist-sw2 | 10.255.1.4/30 |
| Core-SW2 – Dist-sw1 | 10.255.1.8/30 |
| Core-SW2 – Dist-sw2 | 10.255.1.12/30|
| Core-SW1 – EDGE-R1  | 172.16.0.0/30 |
| Core-SW2 – EDGE-R2  | 172.16.0.4/30 |

## ISP Links
| Link | Subnet |
|-------|----------------|
| ISP-1 | 203.0.113.0/30 |
| ISP-2 | 198.51.100.0/30 |
