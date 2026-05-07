# VTP Configuration Lab

## Overview
The VTP Configuration Lab focuses on configuring VLAN Trunking Protocol (VTP) within a Cisco switching environment. This lab demonstrates centralized VLAN management by configuring one switch as a VTP Server and another as a VTP Client to automatically propagate VLAN information across the network.

The objective of this project was to configure VTP domains, secure VTP communication with passwords, and verify automatic VLAN synchronization between switches.

---

## Skills Demonstrated
- VLAN Trunking Protocol (VTP)
- Cisco switch administration
- VLAN propagation
- Centralized VLAN management
- Cisco IOS CLI configuration
- Trunk-based VLAN synchronization
- Network verification and troubleshooting

---

## Technologies Used
- Cisco IOS
- VTP
- VLANs
- Cisco Switches
- 802.1Q Trunking
- Packet Tracer

---

## Lab Objectives
- Configure a VTP Server
- Configure a VTP Client
- Configure a shared VTP domain
- Secure VTP communication with passwords
- Create VLANs on the VTP Server
- Verify VLAN propagation to client switches
- Verify VTP revision number updates

---

# Configure Lab-SW1 as VTP Server

## Configure VTP Mode
```bash
(config)#vtp mode server
```

## Configure VTP Domain
```bash
(config)#vtp domain FSNA
```

## Configure VTP Password
```bash
(config)#vtp password FSNA
```

## Save Configuration
```bash
copy run start
```

## Verify VTP Configuration
```bash
show vtp status
```

### Expected Results
- VTP Mode: Server
- Domain Name: FSNA
- Configuration Revision displayed

---

# Configure Lab-SW2 as VTP Client

## Configure VTP Mode
```bash
(config)#vtp mode client
```

## Configure VTP Domain
```bash
(config)#vtp domain FSNA
```

## Configure VTP Password
```bash
(config)#vtp password FSNA
```

## Save Configuration
```bash
copy run start
```

## Verify VTP Configuration
```bash
show vtp status
```

### Expected Results
- VTP Mode: Client
- Domain Name: FSNA
- Matching revision number

---

# Create VLAN 99 on Lab-SW1

## Create VLAN
```bash
(config)#vlan 99
(config-vlan)#name TEST
```

## Verify VLAN Creation
```bash
show vlan
```

Expected:
- VLAN 99 listed
- VLAN name TEST displayed

---

# Verify VTP Revision Number

## Verify VTP Status
```bash
show vtp status
```

### Expected Results
- Configuration revision number increased
- VLAN database updated

---

# Verify VLAN Propagation to Lab-SW2

## Verify VLAN Database
```bash
show vlan
```

### Expected Results
- VLAN 99 automatically appears on Lab-SW2
- VLAN name TEST synchronized successfully

---

## Verify VTP Revision Number
```bash
show vtp status
```

### Expected Results
- Matching revision number between switches
- Successful VTP synchronization

---

# Verification Tasks

## Verify VTP Operational Status
```bash
show vtp status
```

Expected:
- Correct VTP modes
- Matching domain names
- Matching revision numbers

---

## Verify VLAN Synchronization
```bash
show vlan
```

Expected:
- VLAN 99 present on both switches

---

## Verify Trunk Connectivity
```bash
show interfaces trunk
```

Expected:
- Active trunk links between switches
- VLAN propagation operational

---

# Troubleshooting Concepts Learned
- VTP Server and Client roles
- VLAN database synchronization
- VTP revision numbers
- VTP password authentication
- VTP domain consistency
- VLAN propagation troubleshooting

---

# Business Value
VTP simplifies VLAN administration in enterprise environments by allowing centralized VLAN management across multiple switches. Understanding VTP helps network engineers efficiently manage scalable Layer 2 infrastructures while reducing configuration overhead and administrative errors.

---

# Files Included
- `VTP-Configuration.pkt`
- `Topology.png`
- `Switch1-Config.txt`
- `Switch2-Config.txt`

---

# Author
Jarrod Pettis  
Aspiring Cybersecurity & Network Professional