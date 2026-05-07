# RIPv2 Routing Lab

## Overview
The RIPv2 Routing Lab focuses on configuring Routing Information Protocol Version 2 (RIPv2) across multiple Cisco routers to dynamically exchange routing information between networks. This lab demonstrates dynamic routing concepts, route advertisement, route learning, and routing table verification within a multi-router environment.

The objective of this project was to configure RIPv2 on three routers, establish dynamic route sharing, and verify end-to-end connectivity across multiple networks.

---

## Skills Demonstrated
- Dynamic routing configuration
- RIPv2 deployment
- Cisco IOS routing configuration
- Route advertisement
- Routing table verification
- Network troubleshooting
- Enterprise routing concepts
- Multi-router connectivity

---

## Technologies Used
- Cisco IOS
- RIPv2
- Dynamic Routing
- Cisco Routers
- Packet Tracer

---

## Network Overview

### Router0 Networks
- 10.0.0.0
- 172.16.0.0
- 192.168.252.0

### Router1 Networks
- 192.168.252.0
- 192.168.100.0
- 192.168.101.0

### Router2 Networks
- 192.168.101.0
- 192.168.102.0
- 192.168.103.0

---

# Configure RIPv2 on Router0

## Enable RIP
```bash
(config)#router rip
```

## Configure RIP Version 2
```bash
(config-router)#version 2
```

## Advertise Networks
```bash
(config-router)#network 10.0.0.0
(config-router)#network 172.16.0.0
(config-router)#network 192.168.252.0
```

## Disable Auto-Summarization
```bash
(config-router)#no auto-summary
```

---

# Configure RIPv2 on Router1

## Enable RIP
```bash
(config)#router rip
```

## Configure RIP Version 2
```bash
(config-router)#version 2
```

## Advertise Networks
```bash
(config-router)#network 192.168.252.0
(config-router)#network 192.168.100.0
(config-router)#network 192.168.101.0
```

## Disable Auto-Summarization
```bash
(config-router)#no auto-summary
```

---

# Configure RIPv2 on Router2

## Enable RIP
```bash
(config)#router rip
```

## Configure RIP Version 2
```bash
(config-router)#version 2
```

## Advertise Networks
```bash
(config-router)#network 192.168.101.0
(config-router)#network 192.168.102.0
(config-router)#network 192.168.103.0
```

## Disable Auto-Summarization
```bash
(config-router)#no auto-summary
```

---

# Verification Tasks

## Verify Routing Table
```bash
show ip route
```

### Expected Results
- RIP-learned routes marked with `R`
- Remote networks visible in routing table

---

## Verify RIP Routes
```bash
show ip route rip
```

### Expected Results
- Only RIP-learned routes displayed
- Correct next-hop information present

---

## Verify RIP Database
```bash
show ip rip database
```

### Expected Results
- RIP advertised networks listed
- Learned routes visible

---

## Verify Routing Protocol Configuration
```bash
show ip protocols
```

### Expected Results
- RIP Version 2 enabled
- Advertised networks listed
- Auto-summary disabled

---

## Monitor RIP Events
```bash
debug ip rip events
```

### Expected Results
- RIP updates exchanged between routers
- Route advertisements displayed

---

# Connectivity Testing

## Verify End-to-End Reachability
```bash
ping <destination-ip>
```

### Expected Results
- Successful communication between remote networks
- Dynamic routes functioning correctly

---

# Troubleshooting Concepts Learned
- Dynamic route advertisement
- RIP route propagation
- RIP Version 2 operation
- Auto-summary behavior
- Routing table analysis
- Neighbor route learning
- Multi-hop routing verification

---

# Business Value
Dynamic routing protocols like RIPv2 automate route learning and simplify network scalability in enterprise environments. Understanding dynamic routing concepts is essential for network engineers and cybersecurity professionals responsible for maintaining resilient and efficient routed infrastructures.

---

# Files Included
- `RIPv2-Routing.pkt`
- `Topology.png`
- 

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional