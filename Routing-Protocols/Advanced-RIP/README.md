# Advanced RIP Configuration Lab

## Overview
The Advanced RIP Lab focuses on advanced Routing Information Protocol (RIP) configuration concepts including default route propagation, passive interfaces, RIP timers, and equal-cost multipath routing. This lab demonstrates how RIP can be optimized and controlled within a larger enterprise routing environment.

The objective of this project was to configure advanced RIP features to improve routing efficiency, reduce unnecessary updates, and verify multipath routing behavior.

---

## Skills Demonstrated
- Advanced RIP configuration
- Default route advertisement
- Passive interface configuration
- RIP timer tuning
- Equal-cost multipath routing (ECMP)
- Cisco IOS routing configuration
- Routing optimization
- Network troubleshooting

---

## Technologies Used
- Cisco IOS
- RIPv2
- Dynamic Routing
- Equal-Cost Multipath (ECMP)
- Cisco Routers
- Packet Tracer

---

## Lab Objectives
- Configure RIP default route propagation
- Configure passive RIP interfaces
- View and modify RIP timers
- Verify equal-cost multipath routing
- Configure maximum RIP paths
- Analyze routing behavior

---

# Configure RIP Default Route on Router3

## Enter RIP Configuration
```bash
(config)#router rip
```

## Advertise Default Route
```bash
(config-router)#default-information originate
```

### Expected Results
- Router3 advertises the default route to RIP neighbors
- Other routers learn the gateway of last resort dynamically

---

# Configure RIP Passive Interfaces

## Enter RIP Configuration
```bash
(config)#router rip
```

## Configure Passive Interface
```bash
(config-router)#passive-interface <interface>
```

### Purpose
Passive interfaces:
- Prevent RIP updates from being sent
- Still advertise connected networks internally
- Improve security and reduce unnecessary routing traffic

### Recommended Usage
Configure passive interfaces on:
- LAN interfaces
- Public-facing interfaces
- Networks where RIP neighbors do not exist

---

# View and Configure RIP Timers

## View Current RIP Timers
```bash
show ip protocols
```

### Expected Results
- RIP update timer
- Invalid timer
- Hold-down timer
- Flush timer

---

## Configure RIP Timers
```bash
(config)#configure terminal
(config)#router rip
(config-router)#timers basic 30 180 180 240
```

### Timer Breakdown

| Timer | Value | Purpose |
|---|---|---|
| Update | 30 sec | Sends routing updates |
| Invalid | 180 sec | Route considered invalid |
| Hold-down | 180 sec | Prevents unstable route updates |
| Flush | 240 sec | Removes route from table |

---

# View Equal-Cost Multipath Routing

## Verify Routing Table
```bash
show ip route
```

### Expected Results
- Multiple equal-cost routes visible
- RIP load balancing entries displayed

### Observation
RIP can install multiple equal-cost routes to improve redundancy and load distribution.

---

# Configure Maximum RIP Paths

## View Current Maximum Paths
```bash
show ip protocols
```

### Expected Results
- Current maximum-paths value displayed

---

## Configure Maximum Paths
```bash
(config)#router rip
(config-router)#maximum-paths <number>
```

### Example
```bash
(config-router)#maximum-paths 4
```

### Expected Results
- RIP installs up to specified number of equal-cost routes

---

# Verification Tasks

## Verify Default Route Propagation
```bash
show ip route
```

Expected:
- Gateway of last resort learned through RIP

---

## Verify Passive Interfaces
```bash
show ip protocols
```

Expected:
- Passive interfaces listed

---

## Verify RIP Timers
```bash
show ip protocols
```

Expected:
- Custom timer values displayed

---

## Verify Multipath Routing
```bash
show ip route
```

Expected:
- Multiple equal-cost routes installed

---

## Verify Maximum Paths Configuration
```bash
show ip protocols
```

Expected:
- Maximum-paths value updated

---

# Troubleshooting Concepts Learned
- RIP route propagation control
- Default route advertisement
- Passive interface security benefits
- RIP convergence tuning
- Equal-cost load balancing
- Routing optimization techniques

---

# Business Value
Advanced routing protocol configuration is essential for enterprise network scalability, stability, and redundancy. Understanding RIP optimization techniques strengthens networking and cybersecurity skills required for managing resilient routed infrastructures and troubleshooting complex enterprise routing environments.

---

# Files Included
- `Advanced-RIP.pkt`
- `Topology.png`
- `Router0-Config.txt`
- `Router1-Config.txt`
- `Router2-Config.txt`
- `Router3-Config.txt`
- `Router4-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional