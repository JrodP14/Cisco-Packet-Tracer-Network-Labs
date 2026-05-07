# EIGRP Static Default Route Lab

## Overview
The EIGRP Static Default Route Lab focuses on configuring Enhanced Interior Gateway Routing Protocol (EIGRP) across multiple routers while injecting and advertising a static default route to provide internet connectivity throughout the network. This lab demonstrates dynamic route advertisement, EIGRP neighbor relationships, passive interfaces, and external route redistribution.

The objective of this project was to configure EIGRP routing between routers, establish neighbor adjacencies, redistribute a static default route into EIGRP, and verify full network and internet connectivity. :contentReference[oaicite:0]{index=0}

---

## Skills Demonstrated
- EIGRP configuration
- Dynamic routing
- EIGRP neighbor adjacencies
- Router ID configuration
- Passive interface configuration
- Static default routing
- Route redistribution
- Routing table verification
- Enterprise routing troubleshooting

---

## Technologies Used
- Cisco IOS
- EIGRP
- Static Routing
- Route Redistribution
- Cisco Routers
- Packet Tracer

---

## Network Information

| Router | Router ID |
|---|---|
| R1 | 1.1.1.1 |
| R2 | 2.2.2.2 |
| R3 | 3.3.3.3 |

### EIGRP Autonomous System
```bash
AS Number = 1
```

### Web/DNS Server
```bash
8.8.8.8 (www.test.com)
```

---

# Configure EIGRP on R1

## Enable EIGRP
```bash
(config)#router eigrp 1
(config-router)#eigrp router-id 1.1.1.1
```

## Advertise Networks
```bash
(config-router)#network 10.0.10.0 0.0.0.255
(config-router)#network 192.168.2.0 0.0.0.3
(config-router)#network 192.168.2.8 0.0.0.3
```

## Configure Passive Interface
```bash
(config-router)#passive-interface g0/0
```

---

# Configure EIGRP on R2

## Enable EIGRP
```bash
(config)#router eigrp 1
(config-router)#eigrp router-id 2.2.2.2
```

## Advertise Networks
```bash
(config-router)#network 172.16.20.0 0.0.0.255
(config-router)#network 192.168.2.0 0.0.0.3
(config-router)#network 192.168.2.4 0.0.0.3
(config-router)#network 209.165.200.224 0.0.0.3
```

## Configure Passive Interfaces
```bash
(config-router)#passive-interface g0/0
(config-router)#passive-interface g0/1
```

---

# Configure Static Default Route on R2

## Create Default Route
```bash
(config)#ip route 0.0.0.0 0.0.0.0 209.165.200.225
```

### Purpose
Provides internet access through the ISP router.

---

# Redistribute Static Route into EIGRP

## Advertise Default Route
```bash
(config)#router eigrp 1
(config-router)#redistribute static
```

### Expected Results
- Neighbor routers learn default route dynamically
- Route appears as `D*EX` in routing table

---

# Configure EIGRP on R3

## Enable EIGRP
```bash
(config)#router eigrp 1
(config-router)#eigrp router-id 3.3.3.3
```

## Advertise Networks
```bash
(config-router)#network 192.168.100.0 0.0.0.255
(config-router)#network 192.168.2.4 0.0.0.3
(config-router)#network 192.168.2.8 0.0.0.3
```

## Configure Passive Interface
```bash
(config-router)#passive-interface g0/0
```

---

# Verify EIGRP Neighbor Relationships

## Display EIGRP Neighbors
```bash
show ip eigrp neighbor
```

### Expected Results
- Routers detect neighboring EIGRP peers
- Neighbor adjacencies established successfully

### Example
```bash
R1# show ip eigrp neighbor
```

Expected neighbors:
- 192.168.2.2
- 192.168.2.9

---

# Verify EIGRP Routing Table

## View EIGRP Routes
```bash
show ip route eigrp
```

### Expected Results
- Remote networks learned dynamically
- EIGRP routes marked with `D`
- Default route marked with `D*EX`

---

# Verify Full Routing Table

## Display Routing Table
```bash
show ip route
```

### Expected Results
- Connected routes
- EIGRP learned routes
- Default route present

---

# Important Observation

## External EIGRP Default Route
The default route appears as:
```bash
D*EX 0.0.0.0/0
```

### Meaning
- `D` = EIGRP learned route
- `EX` = External route redistributed into EIGRP
- Administrative Distance = 170

---

# Connectivity Testing

## Verify Host-to-Host Connectivity

### From Host 1
```bash
ping 172.16.20.20
ping 192.168.100.30
```

### From Host 3
```bash
ping 172.16.20.20
```

### Expected Results
- Successful connectivity between all LANs

---

# Verify Internet Connectivity

## Test Web Server Reachability
```bash
ping 8.8.8.8
```

## Verify DNS/Web Access
Browse to:
```text
www.test.com
```

### Expected Results
- Successful internet access
- DNS resolution operational

---

# Verification Tasks

## Verify EIGRP Neighbor Adjacencies
```bash
show ip eigrp neighbor
```

Expected:
- All routers display neighbors correctly

---

## Verify Learned Routes
```bash
show ip route eigrp
```

Expected:
- Multiple EIGRP routes learned dynamically

---

## Verify Protocol Configuration
```bash
show ip protocols
```

Expected:
- EIGRP AS 1 operational
- Passive interfaces listed

---

## Verify Default Route Redistribution
```bash
show ip route
```

Expected:
- `D*EX` default route on R1 and R3
- Static `S*` route on R2

---

# Troubleshooting Concepts Learned
- EIGRP neighbor formation
- Dynamic route advertisement
- Passive interface usage
- Route redistribution
- Default route propagation
- EIGRP external routes
- End-to-end connectivity troubleshooting

---

# Business Value
EIGRP is a scalable enterprise routing protocol used to dynamically exchange routing information and improve network resiliency. Understanding EIGRP neighbor relationships, route redistribution, and default route propagation is essential for network engineers and cybersecurity professionals managing complex routed infrastructures. :contentReference[oaicite:1]{index=1}

---

# Files Included
- `EIGRP-Static-Default-Route.pka`
- `Topology.png`
- `Router1-Config.txt`
- `Router2-Config.txt`
- `Router3-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional