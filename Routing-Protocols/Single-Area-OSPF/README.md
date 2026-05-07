# Single Area OSPF Lab

## Overview
The Single Area OSPF Lab focuses on configuring Open Shortest Path First (OSPF) dynamic routing within a single Area 0 environment. This lab demonstrates OSPF neighbor formation, route advertisement, passive interfaces, and default route propagation for enterprise network connectivity and internet access.

The objective of this project was to configure OSPF routing between three routers, advertise directly connected networks, inject a default route into OSPF, and verify end-to-end connectivity between LANs and an internet-based web server. :contentReference[oaicite:0]{index=0}

---

## Skills Demonstrated
- OSPF configuration
- Single-area OSPF deployment
- Router ID configuration
- OSPF neighbor relationships
- Passive interface configuration
- Default route advertisement
- Dynamic routing verification
- Enterprise routing troubleshooting

---

## Technologies Used
- Cisco IOS
- OSPF
- Dynamic Routing
- Static Default Routes
- Cisco Routers
- Packet Tracer

---

## OSPF Configuration Information

| Router | OSPF Process ID | Router ID |
|---|---|---|
| Boise | 10 | 1.1.1.1 |
| Toledo | 10 | 2.2.2.2 |
| Naperville | 10 | 3.3.3.3 |

### OSPF Area
```bash
Area 0
```

---

# Configure OSPF on Boise Router

## Configure OSPF Process & Router ID
```bash
(config)#router ospf 10
(config-router)#router-id 1.1.1.1
```

---

## Advertise Connected Networks
```bash
(config-router)#network 10.0.10.0 0.0.0.255 area 0
(config-router)#network 192.168.2.0 0.0.0.3 area 0
(config-router)#network 192.168.2.4 0.0.0.3 area 0
(config-router)#network 209.165.200.224 0.0.0.3 area 0
```

---

## Configure Passive Interfaces
```bash
(config-router)#passive-interface g0/0
(config-router)#passive-interface s0/0/0
```

### Purpose
Passive interfaces prevent OSPF hello packets from being sent on:
- LAN interfaces
- Internet-facing interfaces

---

# Configure Static Default Route on Boise

## Create Default Route
```bash
(config)#ip route 0.0.0.0 0.0.0.0 209.165.200.225
```

---

# Advertise Default Route into OSPF

## Inject Default Route
```bash
(config)#router ospf 10
(config-router)#default-information originate
```

### Expected Results
- Neighbor routers learn the default route dynamically
- Route appears as:
```bash
O*E2 0.0.0.0/0
```

---

# Configure OSPF on Toledo Router

## Configure OSPF Process & Router ID
```bash
(config)#router ospf 10
(config-router)#router-id 2.2.2.2
```

---

## Advertise Connected Networks
```bash
(config-router)#network 192.168.100.0 0.0.0.255 area 0
(config-router)#network 192.168.2.0 0.0.0.3 area 0
(config-router)#network 192.168.2.8 0.0.0.3 area 0
```

---

## Configure Passive Interface
```bash
(config-router)#passive-interface g0/0
```

---

# Configure OSPF on Naperville Router

## Configure OSPF Process & Router ID
```bash
(config)#router ospf 10
(config-router)#router-id 3.3.3.3
```

---

## Advertise Connected Networks
```bash
(config-router)#network 172.31.10.0 0.0.0.255 area 0
(config-router)#network 192.168.2.4 0.0.0.3 area 0
(config-router)#network 192.168.2.8 0.0.0.3 area 0
```

---

## Configure Passive Interface
```bash
(config-router)#passive-interface g0/0
```

---

# Verify OSPF Neighbor Relationships

## Display OSPF Neighbors
```bash
show ip ospf neighbor
```

### Expected Results
- Neighbor adjacencies established
- Routers detect neighboring OSPF peers

---

# Verify OSPF Routing Table

## Display Routing Table
```bash
show ip route
```

### Expected Results
- Remote LAN networks learned dynamically
- OSPF routes marked with `O`
- Default route marked with:
```bash
O*E2 0.0.0.0/0
```

---

## View Only OSPF Routes
```bash
show ip route ospf
```

### Expected Results
- Only OSPF-learned routes displayed

---

# Connectivity Testing

## Verify LAN-to-LAN Connectivity

### From Boise PC-B1
```bash
ping 192.168.100.10
ping 172.31.10.10
```

### From Naperville PC-N1
```bash
ping 192.168.100.10
```

### Expected Results
- Successful communication between all LANs

---

# Verify Internet/Web Server Connectivity

## Access Web Server
Open web browser:
```text
www.nexgent.test
```

### Expected Results
- Successful DNS resolution
- Web page loads successfully
- Internet access operational

---

# Verification Tasks

## Verify OSPF Neighbor Adjacencies
```bash
show ip ospf neighbor
```

Expected:
- Neighbor routers displayed correctly

---

## Verify OSPF Learned Routes
```bash
show ip route ospf
```

Expected:
- Remote networks learned dynamically

---

## Verify Default Route Advertisement
```bash
show ip route
```

Expected:
- `O*E2` default route present on Toledo and Naperville

---

## Verify Connectivity
```bash
ping <destination-ip>
```

Expected:
- Successful communication across all LANs and internet

---

# Troubleshooting Concepts Learned
- OSPF neighbor formation
- OSPF route advertisement
- Passive interface security
- Default route injection
- OSPF route table analysis
- Dynamic routing troubleshooting
- End-to-end connectivity validation

---

# Business Value
OSPF is one of the most widely used enterprise dynamic routing protocols due to its scalability, fast convergence, and hierarchical design capabilities. Understanding single-area OSPF routing, default route propagation, and neighbor relationships is essential for network engineers and cybersecurity professionals managing enterprise infrastructures. :contentReference[oaicite:1]{index=1}

---

# Files Included
- `Single-Area-OSPF.pka`
- `Topology.png`
- `Boise-Router-Config.txt`
- `Toledo-Router-Config.txt`
- `Naperville-Router-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional