IP Addressing Plan

Addressing Strategy
	•	Base addressing uses private IP space
	•	Each department is assigned a /26 subnet
	•	Subnet mask: 255.255.255.192
	•	Each subnet provides 62 usable host addresses
	•	VLAN gateways are implemented using HSRP virtual IPs

⸻

First Floor IP Addressing

|Department	|Network	   |Subnet Mask	    |Host Range	                      |Broadcast       |vlan | Active HSRP (FL1-L3 SW)|STANDBY HSRP (FL2-L3 SW)|Virtual GT    |
|-----------|--------------|----------------|---------------------------------|----------------|-----|------------------------|------------------------|--------------|
|Management	|192.168.10.0  |255.255.255.192	|192.168.10.1 – 192.168.10.62	  |192.168.10.63   |10   |192.168.10.2            |192.168.10.3            |192.168.10.1  |
|Research	|192.168.10.64 |255.255.255.192	|192.168.10.65 – 192.168.10.126	  |192.168.10.127  |20   |192.168.10.66           |192.168.10.67           |192.168.10.65 |
|HR         |192.168.10.128|255.255.255.192	|192.168.10.129 – 192.168.10.190  |192.168.10.191  |30   |192.168.10.130          |192.168.10.131          |192.168.10.129|


⸻

Second Floor IP Addressing

|Department	|Network	   |Subnet Mask	    |Host Range	                        |Broadcast       |vlan | Active HSRP (FL1-L3 SW)|STANDBY HSRP (FL2-L3 SW)|Virtual GT    |
|-----------|--------------|----------------|-----------------------------------|----------------|-----|------------------------|------------------------|--------------|
|Marketing	|192.168.10.192|255.255.255.192 |192.168.10.193 – 192.168.10.254    |192.168.10.255  |40   |192.168.10.194          |192.168.10.195          |192.168.10.193|
|Accounts   |192.168.11.0  |255.255.255.192	|192.168.11.1 – 192.168.11.62	    |192.168.11.63   |50   |192.168.11.2            |192.168.11.3            |192.168.11.1  |
|Finance    |192.168.11.64 |255.255.255.192	|192.168.11.65 – 192.168.11.126	    |192.168.11.127  |60   |192.168.11.66           |192.168.11.67           |192.168.11.65 |



⸻

Third Floor IP Addressing

|Department	|Network	    |Subnet Mask	  |Host Range	                     |Broadcast       |vlan | Active HSRP (FL3-L3 SW)|STANDBY HSRP (FL4-L3 SW) |Virtual GT   |
|-----------|---------------|-----------------|----------------------------------|----------------|-----|------------------------|------------------------|--------------|
|Logistics	|192.168.11.128 |255.255.255.192  |192.168.11.129 – 192.168.11.190   |192.168.11.191  |70   |192.168.11.130          |192.168.11.131          |192.168.11.129|
|Customer   |192.168.11.192 |255.255.255.192  |192.168.11.193 – 192.168.11.254   |192.168.11.255  |80   |192.168.11.194          |192.168.11.195          |192.168.11.193|
|Guest      |192.168.12.0   |255.255.255.192  |192.168.12.1 – 192.168.12.62      |192.168.12.63   |90   |192.168.12.2            |192.168.12.3            |192.168.12.1  |
    



⸻

Fourth Floor IP Addressing
|Department	|Network	    |Subnet Mask	  |Host Range	                     |Broadcast       |vlan | Active HSRP (FL3-L3 SW)|STANDBY HSRP (FL4-L3 SW) |Virtual GT    |
|-----------|---------------|-----------------|----------------------------------|----------------|-----|------------------------|-------------------------|--------------|
|Admin	    |192.168.12.64  |255.255.255.192  |192.168.12.65 – 192.168.12.126    |192.168.12.127  |100  |192.168.12.66           |192.168.12.67            |192.168.12.65 |
|ICT        |192.168.12.128 |255.255.255.192  |192.168.12.129 – 192.168.12.190   |192.168.12.191  |110  |192.168.12.130          |192.168.12.131           |192.168.12.129|
|Server Room|192.168.12.192 |255.255.255.192  |192.168.12.193 – 192.168.12.254   |192.168.12.255  |129  |192.168.12.194          |192.168.12.195           |192.168.12.193|
    


⸻

    Core to Distribution Layer IP Addressing

To provide scalable and efficient routing between the Core Layer and Distribution (Layer 3) switches, point-to-point /30 subnets are used.

Using /30 networks:
	•	Minimizes IP address waste
	•	Provides exactly two usable IPs per link
	•	Is best practice for routed infrastructure links
	•	Improves routing table efficiency

⸻

Addressing Strategy
	•	Each Core–Distribution link uses a unique /30 subnet
	•	One IP is assigned to the Core Router
	•	One IP is assigned to the Distribution (L3) Switch
	•	Routing is handled using OSPF Area 0

VLAN and Inter-VLAN Routing
	•	Each department is mapped to a unique VLAN
	•	Layer 3 switches provide inter-VLAN routing using SVIs
	•	Trunk links are configured between access and distribution switches
	•	Only required VLANs are allowed on trunks for security

⸻

Gateway Redundancy with HSRP

To ensure high availability, HSRP is configured on distribution layer switches.

Example HSRP Design (VLAN 10)

Device	IP Address
Floor Switch A	192.168.10.2
Floor Switch B	192.168.10.3
Virtual Gateway	192.168.10.1

Clients use the virtual IP as their default gateway.

HSRP provides:
	•	Automatic failover
	•	No single point of failure
	•	Seamless user connectivity

⸻

Routing Design
	•	OSPF (Area 0) is used between core and distribution layers
	•	All VLAN networks are advertised into OSPF
	•	Point-to-point /30 networks are used between routing devices
	•	OSPF ensures dynamic path selection and fast convergence

⸻

DHCP Design
	•	Central DHCP server located in the Server Room
	•	All VLAN interfaces use DHCP relay
	•	Example DHCP relay configuration:

ip helper-address 192.168.12.196

This allows all departments to obtain IP addresses dynamically.

⸻

Testing and Verification

The following tests were successfully performed:
	•	Inter-VLAN communication
	•	Floor-to-floor connectivity
	•	End-to-end ping tests
	•	DHCP address assignment
	•	HSRP failover simulation
	•	OSPF adjacency verification

⸻

Tools Used
	•	Cisco Packet Tracer
	•	Cisco IOS CLI
	•	GitHub for documentation and version control

⸻

Author

Oluwafemi Gabriel
Aspiring Network Engineer
Cisco Packet Tracer Projects Portfolio
