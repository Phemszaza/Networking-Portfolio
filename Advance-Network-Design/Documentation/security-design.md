# Security Design

## Firewall Zones
The firewall implements three security zones:
- Outside: Internet-facing interfaces
- Inside: Internal users and trusted services
- DMZ: Public-facing servers

## Security Controls
- VLAN segmentation
- ACLs for management access
- SSH-only remote administration
- Guest VLAN isolation
