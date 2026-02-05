# Routing and Redundancy

## Routing Protocol
OSPF is used as the internal routing protocol across:
- Core switches
- Layer 2 access switches
- Firewalls

## Gateway Redundancy
HSRP is configured on all user VLANs:
- Virtual IP acts as the default gateway
- One switch is Active
- One switch is Standby

This allows seamless failover during device failure.

## Link Redundancy
EtherChannel with LACP is used between core switches to:
- Increase bandwidth
- Provide link-level redundancy/
