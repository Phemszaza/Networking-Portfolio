# Routing Design

## Interior Routing
OSPF is used internally between core and distribution switches.

- Area 0
- Point-to-point links
- Default routes injected from core layer

## Edge Routing
Edge routers use static default routes toward their ISPs.

## Asymmetric Routing
When both ISPs are active, traffic may exit through one ISP and return through another.
This can cause intermittent packet loss due to NAT state mismatch.
