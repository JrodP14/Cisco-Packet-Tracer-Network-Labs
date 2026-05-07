# VLAN Creation Lab

## Overview
The VLAN Creation Lab focuses on configuring Virtual Local Area Networks (VLANs) on a Cisco switch to segment network traffic and improve network organization. This lab demonstrates VLAN creation, access port assignment, and Layer 2 communication behavior between devices in different VLANs.

The objective of this project was to configure multiple VLANs, assign switchports to the correct VLANs, and verify host connectivity within and across VLAN boundaries.

---

## Skills Demonstrated
- VLAN creation and management
- Access port configuration
- Layer 2 segmentation
- Cisco IOS CLI configuration
- Network isolation concepts
- Host connectivity testing
- Basic network troubleshooting
- Enterprise switch administration

---

## Technologies Used
- Cisco IOS
- VLANs
- Cisco Switches
- Packet Tracer

---

## VLAN Configuration

| VLAN ID | VLAN Name |
|---|---|
| 100 | DATA-1 |
| 200 | DATA-2 |

---

# Configure VLANs on Lab-Switch

## Create VLAN 100
```bash
(config)#vlan 100
(config-vlan)#name DATA-1
```

## Create VLAN 200
```bash
(config)#vlan 200
(config-vlan)#name DATA-2
```

## Verify VLAN Creation
```bash
show vlan
```

Expected:
- VLANs 100 and 200 appear in VLAN database
- VLAN names correctly assigned

---

# Configure Access Ports for VLAN 100

## Configure Interfaces Fa0/1 - Fa0/12
```bash
(config)#interface range fa0/1 - 12
(config-if-range)#description Access Port
(config-if-range)#switchport mode access
(config-if-range)#switchport access vlan 100
```

## Verify Configuration
```bash
do show running-config
```

Expected:
- Interfaces assigned to VLAN 100
- Access mode enabled

---

# Configure Access Ports for VLAN 200

## Configure Interfaces Fa0/13 - Fa0/24
```bash
(config)#interface range fa0/13 - 24
(config-if-range)#description Access Port
(config-if-range)#switchport mode access
(config-if-range)#switchport access vlan 200
```

## Verify Configuration
```bash
do show running-config
```

Expected:
- Interfaces assigned to VLAN 200
- Access mode enabled

---

# Connect Hosts to Appropriate Ports

| Host | Switch Port | VLAN |
|---|---|---|
| PC1 | Fa0/1 | VLAN 100 |
| PC2 | Fa0/2 | VLAN 100 |
| PC3 | Fa0/13 | VLAN 200 |
| PC4 | Fa0/14 | VLAN 200 |

---

# Connectivity Testing

## Test Layer 3 Reachability

### Ping Tests
```bash
ping 192.168.100.50
ping 192.168.100.51
ping 10.10.10.50
ping 10.10.10.51
```

---

# Verification Results

## Were all host computers able to ping one another?
### Result:
```text
No
```

---

## Why were some PCs unable to communicate?
### Explanation:
PC1 and PC2 could not ping PC3 or PC4 because:
- They were placed in different VLANs
- They belonged to different IP networks
- No inter-VLAN routing was configured

---

## Were hosts in the same VLAN able to communicate?
### Result:
```text
Yes
```

---

## Why were hosts in the same VLAN able to communicate?
### Explanation:
Hosts within the same VLAN share the same Layer 2 broadcast domain and IP network, allowing direct communication without routing.

---

# Verification Tasks

## Verify VLAN Database
```bash
show vlan
```

Expected:
- VLAN 100 and VLAN 200 listed
- Correct interfaces assigned

---

## Verify Interface Configuration
```bash
show running-config
```

Expected:
- Access ports configured correctly
- VLAN assignments visible

---

## Verify Connectivity
```bash
ping <destination-ip>
```

Expected:
- Successful communication within same VLAN
- Failed communication across VLANs

---

# Troubleshooting Concepts Learned
- VLAN segmentation behavior
- Broadcast domain separation
- Access port configuration
- Same-VLAN communication
- Inter-VLAN communication limitations
- Basic VLAN troubleshooting

---

# Business Value
VLANs are a core enterprise networking technology used to segment traffic, improve security, reduce broadcast domains, and organize users logically across a network. Understanding VLAN configuration and communication boundaries is essential for network administration, infrastructure engineering, and cybersecurity operations.

---

# Files Included
- `VLAN-Creation.pkt`
- `Topology.png`
- `Switch-Config.txt`
- `PC1-Addressing.txt`
- `PC2-Addressing.txt`
- `PC3-Addressing.txt`
- `PC4-Addressing.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional