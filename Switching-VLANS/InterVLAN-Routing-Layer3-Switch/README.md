# InterVLAN Routing – Layer 3 Switch Lab

## Overview
The InterVLAN Routing Lab focuses on configuring a Cisco Layer 3 switch to perform routing between VLANs using Switch Virtual Interfaces (SVIs). This lab demonstrates how a multilayer switch can provide gateway services and enable communication between separate VLANs without requiring an external router.

The objective of this project was to configure VLAN interfaces, assign gateway IP addresses, enable Layer 3 routing, and verify successful communication between devices in different VLANs.

---

## Skills Demonstrated
- Layer 3 switch configuration
- InterVLAN routing
- Switch Virtual Interface (SVI) configuration
- VLAN gateway deployment
- Cisco IOS CLI configuration
- Routing table verification
- Network troubleshooting
- Enterprise switching concepts

---

## Technologies Used
- Cisco IOS
- Layer 3 Switching
- VLANs
- SVIs
- InterVLAN Routing
- Packet Tracer

---

## VLAN & Gateway Information

| VLAN | Network | Gateway |
|---|---|---|
| VLAN 100 | 192.168.100.0/24 | 192.168.100.1 |
| VLAN 200 | 10.10.10.0/24 | 10.10.10.1 |

---

# Configure VLAN Interfaces on Lab-SW1

## Configure VLAN 100 Interface
```bash
(config)#interface vlan 100
(config-if)#ip address 192.168.100.1 255.255.255.0
(config-if)#description VLAN 100 gateway
```

---

## Configure VLAN 200 Interface
```bash
(config)#interface vlan 200
(config-if)#ip address 10.10.10.1 255.255.255.0
(config-if)#description VLAN 200 gateway
```

---

## Save Configuration
```bash
copy run start
```

---

# Verify Layer 3 Interface Configuration

## Verify Running Configuration
```bash
show running-config
```

Expected:
- VLAN 100 and VLAN 200 interfaces configured
- Correct IP addresses assigned

---

## Verify Interface Status
```bash
show ip interface brief
```

Expected:
- VLAN 100 = up/up
- VLAN 200 = up/up

---

# Test Connectivity from Lab-SW1

## Ping VLAN 100 Hosts
```bash
ping 192.168.100.50
ping 192.168.100.51
```

---

## Ping VLAN 200 Hosts
```bash
ping 10.10.10.50
ping 10.10.10.51
```

### Expected Results
- Successful pings to all hosts
- Switch can reach devices in both VLANs

---

# Important Observation Before Routing

### Initial State
Even though the Layer 3 switch has gateway IPs configured:
- PCs in different VLANs still cannot communicate
- InterVLAN routing is not enabled yet

---

# Enable IP Routing on Lab-SW1

## Enable Routing
```bash
(config)#ip routing
```

---

## Verify Routing Table
```bash
show ip route
```

### Expected Results
- Connected routes for VLAN 100 and VLAN 200
- Routing table populated with SVI networks

---

# Test InterVLAN Connectivity

## From PC1
```bash
ping 10.10.10.50
ping 10.10.10.51
```

---

## From PC3
```bash
ping 192.168.100.50
ping 192.168.100.51
```

### Expected Results
- Successful communication between VLANs
- InterVLAN routing operational

---

# Additional Verification

## Verify Default Gateway Reachability
Hosts should successfully ping:
```bash
192.168.100.1
10.10.10.1
```

---

## Verify Routing Table
```bash
show ip route
```

Expected:
- VLAN networks listed as directly connected

---

## Verify Interface Status
```bash
show ip interface brief
```

Expected:
- VLAN interfaces operational

---

# Verification Tasks

## Verify SVI Configuration
```bash
show running-config
```

Expected:
- Correct SVI IP addressing
- VLAN descriptions configured

---

## Verify InterVLAN Routing
```bash
ping <remote-vlan-host>
```

Expected:
- Successful communication across VLANs

---

## Verify Routing Table
```bash
show ip route
```

Expected:
- Routing entries for VLAN networks

---

# Troubleshooting Concepts Learned
- Switch Virtual Interface (SVI) operation
- Layer 3 switching concepts
- InterVLAN routing behavior
- VLAN gateway configuration
- Routing table verification
- Cross-VLAN connectivity troubleshooting

---

# Business Value
InterVLAN routing is a foundational enterprise networking technology that allows secure communication between segmented networks. Layer 3 switches provide high-performance routing capabilities commonly used in enterprise campuses, data centers, and corporate infrastructures to improve scalability, efficiency, and network segmentation.

---

# Files Included
- `InterVLAN-Routing-Layer3-Switch.pkt`
- `Topology.png`
- `Switch1-Layer3-Config.txt`
- `Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional