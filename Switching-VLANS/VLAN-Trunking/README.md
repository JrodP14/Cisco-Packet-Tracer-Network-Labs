# VLAN Trunking Lab

## Overview
The VLAN Trunking Lab focuses on configuring trunk links between Cisco switches to allow multiple VLANs to traverse a single physical connection. This lab demonstrates how VLAN traffic is extended across switches while maintaining VLAN segmentation and communication boundaries.

The objective of this project was to configure switch trunk ports, verify trunk operation, and validate host communication across switches within the same VLANs.

---

## Skills Demonstrated
- VLAN trunk configuration
- Switch-to-switch connectivity
- 802.1Q trunking
- Cisco IOS CLI configuration
- VLAN traffic forwarding
- Layer 2 network expansion
- Connectivity verification
- Network troubleshooting

---

## Technologies Used
- Cisco IOS
- VLANs
- 802.1Q Trunking
- Cisco Switches
- Packet Tracer

---

## Lab Objectives
- Configure trunk ports on Cisco switches
- Establish switch-to-switch trunk connectivity
- Verify trunk operational status
- Extend VLANs across multiple switches
- Validate same-VLAN communication across trunk links
- Observe VLAN communication limitations without routing

---

# Configure Trunk Port on Lab-SW1

## Configure Interface G0/1
```bash
(config)#interface g0/1
(config-if)#description Trunk to SW2
(config-if)#switchport mode trunk
```

## Save Configuration
```bash
copy run start
```

---

# Configure Trunk Port on Lab-SW2

## Configure Interface G0/1
```bash
(config)#interface g0/1
(config-if)#description Trunk to SW1
(config-if)#switchport mode trunk
```

## Save Configuration
```bash
copy run start
```

---

# Connect the Trunk Link

## Physical Connection
- Connect Lab-SW1 G0/1 to Lab-SW2 G0/1
- Use an Ethernet crossover cable

---

# Verify Trunk Operation

## Verify Trunk Status
```bash
show interfaces trunk
```

### Expected Results
- Interface G0/1 listed as trunking
- 802.1Q encapsulation active
- VLANs allowed across the trunk

---

# Connect Hosts to Lab-SW2

| Host | Switch | Port | VLAN |
|---|---|---|---|
| PC2 | Lab-SW2 | Fa0/1 | VLAN 100 |
| PC4 | Lab-SW2 | Fa0/13 | VLAN 200 |

---

# Connectivity Testing

## Test Same-VLAN Connectivity Across Trunk

### VLAN 100 Test
```bash
ping 192.168.100.51
```

Expected:
- PC1 and PC2 communicate successfully

---

### VLAN 200 Test
```bash
ping 10.10.10.51
```

Expected:
- PC3 and PC4 communicate successfully

---

# Important Observation

## Cross-VLAN Communication
Devices in different VLANs still cannot communicate because:
- No inter-VLAN routing is configured
- VLANs remain separate broadcast domains
- Trunking extends VLANs but does not route traffic

---

# Verification Tasks

## Verify Trunk Interfaces
```bash
show interfaces trunk
```

Expected:
- G0/1 operational as trunk
- VLANs passing across trunk link

---

## Verify VLAN Database
```bash
show vlan
```

Expected:
- VLAN 100 and VLAN 200 present on both switches

---

## Verify Interface Configuration
```bash
show running-config
```

Expected:
- Trunk configuration visible on G0/1

---

## Verify Host Connectivity
```bash
ping <destination-ip>
```

Expected:
- Successful same-VLAN communication
- Failed cross-VLAN communication

---

# Troubleshooting Concepts Learned
- 802.1Q trunk operation
- VLAN propagation across switches
- Same-VLAN communication over trunk links
- Broadcast domain separation
- Trunk verification procedures
- Layer 2 traffic segmentation

---

# Business Value
VLAN trunking is essential in enterprise environments where VLANs span multiple switches and departments. Understanding trunk configuration enables scalable network design, efficient traffic segmentation, and proper Layer 2 infrastructure deployment used in modern enterprise and data center networks.

---

# Files Included
- `VLAN-Trunking-Lab.pkt`
- `Topology.png`
- `Switch1.txt`
- `Switch2.txt`
- `PC1-Addressing.txt`
- `PC2-Addressing.txt`
- `PC3-Addressing.txt`
- `PC4-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional