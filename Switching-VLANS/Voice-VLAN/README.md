# Voice VLAN Configuration Lab

## Overview
The Voice VLAN Lab focuses on configuring separate VLANs for voice and data traffic on Cisco switches. This lab demonstrates how Cisco IP phones and user devices can share the same physical switchport while maintaining traffic separation using Voice VLAN technology.

The objective of this project was to configure dedicated voice and data VLANs, assign switch access ports appropriately, and verify proper switchport operation for converged network environments.

---

## Skills Demonstrated
- VLAN configuration
- Voice VLAN implementation
- Access port configuration
- Cisco IP telephony support
- Cisco IOS CLI configuration
- Layer 2 traffic segmentation
- Enterprise switch configuration
- Network verification and troubleshooting

---

## Technologies Used
- Cisco IOS
- VLANs
- Voice VLANs
- Cisco Switches
- Cisco IP Phones
- Packet Tracer

---

## Lab Objectives
- Create separate Data and Voice VLANs
- Configure access ports for converged traffic
- Assign data VLANs to user devices
- Assign voice VLANs to IP phones
- Verify switchport VLAN assignments
- Understand enterprise voice network segmentation

---

# VLAN Configuration

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 10 | Data | User Data Traffic |
| 20 | Voice | IP Phone Traffic |

---

# Create the Data and Voice VLANs

## Configure VLAN 10
```bash
(config)#vlan 10
(config-vlan)#name Data
(config-vlan)#exit
```

---

## Configure VLAN 20
```bash
(config)#vlan 20
(config-vlan)#name Voice
(config-vlan)#end
```

### Expected Results
- VLAN 10 created for data traffic
- VLAN 20 created for voice traffic

---

# Configure Access Port on SW-1

## Configure Interface Fa0/1
```bash
(config)#interface fa0/1
(config-if)#switchport mode access
(config-if)#switchport access vlan 10
(config-if)#switchport voice vlan 20
(config-if)#end
```

### Purpose
- Data devices connected through the phone use VLAN 10
- Cisco IP phones use VLAN 20 for voice traffic

---

# Verify Switchport Configuration

## Verify Switchport Settings
```bash
show interfaces fa0/1 switchport
```

### Expected Results
- Administrative Mode: static access
- Access Mode VLAN: 10
- Voice VLAN: 20

---

## Verify Running Configuration
```bash
show running-configuration
```

### Expected Results
- Voice VLAN configuration visible
- Access VLAN configuration present

---

# Verification Tasks

## Verify VLAN Database
```bash
show vlan
```

Expected:
- VLAN 10 and VLAN 20 listed
- Correct VLAN names displayed

---

## Verify Switchport Configuration
```bash
show interfaces fa0/1 switchport
```

Expected:
- Access VLAN = 10
- Voice VLAN = 20

---

## Verify Running Configuration
```bash
show running-config
```

Expected:
- Interface Fa0/1 configured properly
- Voice VLAN commands visible

---

# Troubleshooting Concepts Learned
- Voice VLAN operation
- Data vs voice traffic separation
- Access port configuration
- Cisco IP phone VLAN tagging
- Converged network infrastructure
- VLAN verification procedures

---

# Business Value
Voice VLANs are commonly deployed in enterprise networks to separate voice traffic from user data traffic for improved security, quality of service (QoS), and traffic management. Understanding Voice VLAN configuration is essential for network administrators and infrastructure engineers supporting modern converged voice and data environments.

---

# Files Included
- `Voice-VLAN.pkt`
- `Topology.png`
- `Switch0-Config.txt`
- `Switch1-Config.txt`
- `Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional