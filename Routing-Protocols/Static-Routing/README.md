# Static Routing Lab

## Overview
The Static Routing Lab focuses on configuring IPv4 addressing and verifying connectivity between routed network interfaces. This lab demonstrates foundational router configuration concepts including interface addressing, interface activation, and basic network reachability verification.

The objective of this project was to configure router interfaces for multiple LANs and validate Layer 3 connectivity between network segments.

---

## Skills Demonstrated
- Cisco router configuration
- IPv4 addressing
- Interface configuration
- Layer 3 connectivity
- Cisco IOS CLI usage
- Network verification
- Routing fundamentals
- Troubleshooting connectivity issues

---

## Technologies Used
- Cisco IOS
- IPv4 Routing
- Cisco Routers
- Packet Tracer

---

## Network Information

| Interface | Network | IP Address |
|---|---|---|
| G0/0 | LAN 1 | 10.20.30.1/24 |
| G0/1 | LAN 2 | 172.16.50.1/24 |

---

# Configure IP Addresses on Router0

## Configure LAN 1 Interface G0/0
```bash
(config)#interface GigabitEthernet0/0
(config-if)#no shutdown
(config-if)#ip address 10.20.30.1 255.255.255.0
```

### Expected Results
- Interface becomes operational
- Gateway established for LAN 1

---

## Configure LAN 2 Interface G0/1
```bash
(config)#interface GigabitEthernet0/1
(config-if)#no shutdown
(config-if)#ip address 172.16.50.1 255.255.255.0
```

### Expected Results
- Interface becomes operational
- Gateway established for LAN 2

---

# Verify Configured IP Addresses

## Verify Interface Status
```bash
show ip interface brief
```

### Expected Results
- G0/0 = up/up
- G0/1 = up/up
- Correct IP addresses displayed

---

## Verify Running Configuration
```bash
show running-config
```

### Expected Results
- Interface IP addresses configured correctly
- Interfaces enabled with `no shutdown`

---

# Confirm IP Connectivity

## Test Reachability
```bash
ping <ip address>
```

### Example Tests
```bash
ping 10.20.30.1
ping 172.16.50.1
```

### Expected Results
- Successful ping replies
- Interfaces reachable from connected hosts

---

# Verification Tasks

## Verify Interface Operational Status
```bash
show ip interface brief
```

Expected:
- Both interfaces operational
- Correct addressing configured

---

## Verify Router Configuration
```bash
show running-config
```

Expected:
- IP addresses assigned properly
- Interfaces enabled

---

## Verify Connectivity
```bash
ping <destination-ip>
```

Expected:
- Successful connectivity between devices and router interfaces

---

# Troubleshooting Concepts Learned
- Interface activation using `no shutdown`
- IPv4 interface addressing
- Layer 3 verification techniques
- Connectivity testing
- Router interface troubleshooting
- Basic routing concepts

---

# Business Value
Static routing and interface configuration are foundational networking skills required in enterprise IT, network administration, and cybersecurity operations. Understanding how routers forward traffic between networks is critical for troubleshooting connectivity and building secure network infrastructures.

---

# Files Included
- `Static-Routing.pkt`
- `Topology.png`
- `Router0-Config.txt`
- `Router1-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional