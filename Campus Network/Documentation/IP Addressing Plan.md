IP Addressing Plan

Project: Albion University Campus Network

⸻

1. Main Campus VLANs

Building A, Administration and Business Faculty

|VLAN ID|	Department          |	Subnet	        | Default Gateway  |	Addressing|
|10	    | Management (Admin)	| 192.168.1.0/24	| 192.168.1.1	     |   DHCP     |
|20	    | Human Resources	    | 192.168.2.0/24	| 192.168.2.1	     |   DHCP     |
|30	    | Finance	            | 192.168.3.0/24	| 192.168.3.1	     |   DHCP     |
|40     | Business Faculty  	| 192.168.4.0/24	| 192.168.4.1	     |   DHCP     |


⸻

Building B, Engineering and Art & Design

|VLAN ID|	Department              |	Subnet	        | Default Gateway  |	Addressing|
|50	    | Engineering & Computing	| 192.168.5.0/24	| 192.168.5.1	     | DHCP       |
|60	    |Art & Design	            | 192.168.6.0/24	|192.168.6.1	     | DHCP       |


⸻

Building C, Student Labs and IT Department

|VLAN ID|	Department            |	Subnet	        | Default Gateway  |	Addressing|
|70	    |Student Labs	          |192.168.7.0/24	  |192.168.7.1	     |DHCP
|80	    |IT Department	        |192.168.8.0/24   |192.168.8.1	     |DHCP
|80    	|Web & FTP Servers	    |192.168.8.0/24	  |192.168.8.1	     |Static(192.168.8.4) (192.168.8.5))


⸻

2. Branch Campus VLANs

Faculty of Health and Sciences

|VLAN ID|	Department                 |	Subnet	        | Default Gateway  |	Addressing|
|90	    |Health Science Staff	       |192.168.10.0/24  	| 192.168.10.1	   | DHCP       |
|100	  |Health Science Student Labs |192.168.11.0/24	  | 192.168.11.1	   | DHCP       |


⸻

3. Inter-Campus WAN Link

|Link	                              |    Subnet	    |Device A	  |Device B   |
|Main Campus Router ↔ Branch Router |10.10.10.0/30	|10.10.10.1	|10.10.10.2 |


⸻

4. External Cloud Network

Network	Purpose
20.0.0.0/30	External Email Server (Cloud)

|Device	      |IP Address  |
|Cloud Router	|20.0.0.1    |
|Email Server	|20.0.0.2    |

Static routing is used from the campus router to reach the external cloud network.

⸻

5. Addressing Summary
	•	Each department is isolated using VLANs
	•	/24 subnets provide sufficient host capacity
	•	DHCP is used for end-user devices
	•	Servers and network infrastructure use static IPs
	•	RIPv2 advertises internal networks
	•	Static route provides access to the external email server

⸻
